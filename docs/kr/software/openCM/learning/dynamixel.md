# 다이나믹셀 사용법

아래의 예제에 사용된 다이나믹셀은 ID=1번, 통신 속도는 모두 1M bps로 초기화를 전제로 합니다.
다이나믹셀 클래스 선언은 명시되어 있지 않더라도 아래와 같이 미리 선언되어 있다고 가정합니다.

**Dynamixel Dxl(1); // Dynamixel Bus on Serial1(USART1)**

1. AX-12A의 모델 넘버와 펌웨어 버전을 읽습니다.
   E-manual에서 AX-12A의 Control Table에서 모델넘버와 펌웨어 버전에 해당하는 주소값은 아래와 같습니다.
   ![opencm9.04_dynamixel.png](/assets/images/sw/opencm/opencm9.04_dynamixel.png)
   ID가 1번인 AX-12A에서 모델 넘버의 하위바이트에 해당하는 0번 주소와 펌웨어 버전 정보에 해당하는 2번주소를 읽어보겠습니다.
   모두 1바이트이므로 byte형 타입의 변수를 쓰면 됩니다.
   ```
   byte nModel = Dxl.readByte(1, 0); // 모델 번호를 읽고
   byte vFirmware = Dxl.readByte(1, 2); // 펌웨어 버전을 읽습니다.
   ```
   아래와 같이 출력합니다.
   ```
   SerialUSB.print(“Model Number : “);SerialUSB.print(nModel);
   SerialUSB.print(“ Firmware Ver : “);SerialUSB.println(vFirmware);
   ```
   ![opencm9.04_dynamixel1.png](/assets/images/sw/opencm/opencm9.04_dynamixel1.png)
   <출력 확인>
2.  ID가 1인 AX-12A의 현재 내부 온도를 읽어봅니다.
   Control Table에서 AX-12A의 내부온도에 해당하는 주소는 아래와 같습니다.
   ![opencm9.04_dynamixel2.png](/assets/images/sw/opencm/opencm9.04_dynamixel2.png)
   같은 방식으로 readByte()로 한바이트 읽어 봅니다.
   byte temp = Dxl.readByte(1, 43);
   SerialUSB.print(“Current Temperature : “);SerialUSB.println(temp);
3. AX-12의 ID를 2로 설정합니다.
   다이나믹셀 ID에 해당하는 3번 주소에 writeByte() 메소드로 1바이트 기록합니다.
   ![opencm9.04_dynamixel3.png](/assets/images/sw/opencm/opencm9.04_dynamixel3.png)
    <br />
   ```
   void setup(){
     Dxl.begin(1);
     delay(1000);  // 1초정도 딜레이를 주는 것이 좋습니다.
     Dxl.writeByte(1, 3, 2); //1번 ID의 다이나믹셀을 2번 ID로 변경
   }
   void loop(){
     Dxl.writeByte(2, 25, 1);  //변경된 ID로 LED Blinking
     delay(100);
     Dxl.writeByte(2, 25, 0);
     delay(100);
   }
   ```
   성공적으로 ID변경이 완료되면 다이나믹셀의 LED가 깜빡이게 될 것 입니다.
4. Baud Rate를 57600 bps로 변경합니다.
   다이나믹셀의 통신속도는 4번 주소의 Baud rate를 이용해 변경 가능합니다. ID 변경과 마찬가지로 writByte() 메소드를 활용합니다.
   57600 bps는 다이나믹셀 속도 계산을 활용하면 index 값이 34가 나옵니다. 다이나믹셀 2.0 프로토콜의 경우는 새로운 Baud rate 테이블을 참고하세요 57600bps의 경우 1이 됩니다.
   ![opencm9.04_dynamixel4.png](/assets/images/sw/opencm/opencm9.04_dynamixel4.png)
   <br/>
   ```
   void setup(){
     Dxl.begin(1);
     delay(1000);  // 1초정도 딜레이를 주는 것이 좋습니다.
     Dxl.writeByte(1, 4, 34); // 34 = 57600 bps
     Dxl.begin(34); // 변경되 Baud rate로 새롭게 초기화
     delay(1000);
   }
   void loop(){
     Dxl.writeByte(1, 25, 1);  
     delay(100);
     Dxl.writeByte(1, 25, 0);
     delay(100);
   }
   ```
   Baud rate가 변경되었으므로 새롭게 Dxl.begin(34)로 버스를 새롭게 초기화해야 합니다.
5. ID가 1인 다이나믹셀의 움직임 유무를 확인합니다.
   Control Table에서 46(0x2E)값을 이용해 현재 AX-12A의 움직임 여부를 확인할 수 있습니다.
   ![opencm9.04_dynamixel5.png](/assets/images/sw/opencm/opencm9.04_dynamixel5.png)
   <br/>
   ```
   byte bMoving = Dxl.readByte(1, 46);
   ```
   ID 1번 다이나믹셀이 현재 움직이고 있다면 bMoving이라는 변수에 1이 반환되고 움직임이 없다면 0을 반환합니다.
6. AX-12A 다이나믹셀을 150도 위치로 움직여 봅니다.
   다이나믹셀을 목표 위치(150도)로 움직이려면 Goal Position에 해당하는 주소에 원하는 이동 위치를 넣어주면 됩니다.
   아래와 같이 하위, 상위 2바이트로 이루어져 있으며 각각 접근하는 것 보다는 하위 바이트 30(0x1E)에 writeWord() 메소드를 통해 2바이트(1워드)를 기록하는 것을 추천합니다.
   ![opencm9.04_dynamixel6.png](/assets/images/sw/opencm/opencm9.04_dynamixel6.png)
   E-manual에서 150도에 해당하는 위치는 아래의 그림과 같이 512 와 매칭됨을 확인할 수 있습니다.   
   ![opencm9.04_dynamixel7.png](/assets/images/sw/opencm/opencm9.04_dynamixel7.png)
   <br/>
   ```
   Dxl.writeWord(1, 30, 512);
   Dxl.getResult() 함수로 통신 성공 여부를 확인하시길 바랍니다.
   ```
7. 각의 RX-64에 대해서 각각 다음의 위치와 속도로 이동합니다. 이동이 완료되면 모두 0위치로 원위치합니다. 계속 반복적으로 이와 같은 동작을 수행합니다.
   ![opencm9.04_dynamixel8.png](/assets/images/sw/opencm/opencm9.04_dynamixel8.png)
   각 다이나믹셀에 보내기 위한 Sync Write 패킷 데이터를 만듭니다. 0위치에 대한 Sync Write 패킷 데이터와 목표위치와 속도를 저장한 패킷 데이터를 만듭니다.
   ```
   #define PACKET_LEN 12
   #define NUM_OF_DATA 2

   int SyncPage1[PACKET_LEN]=
   {  1, 010, 150,
     2, 220, 360,
     3, 020, 170
     4, 220, 380};

   int SyncPage2[PACKET_LEN]=
   {  1, 0, 0,
     2, 0, 0,
     3, 0, 0
     4, 0, 0};
   void loop(){
      Dxl.syncWrite(30, NUM_OF_DATA, SyncPage1, PACKET_LEN);
      delay(1000);
      Dxl.syncWrite(30, NUM_OF_DATA, SyncPage2, PACKET_LEN);
      delay(1000);
   }
   ```
8. 동작각을 0~150도로 제한합니다.
   CCW Angle Limit이 0x3FF일 경우 300도 이므로 150도에 해당하는 0x200을 writeByte() 메소드를 이용해 전송합니다.
   주의 : 8번 CCW Angle Limit을 0으로 할 경우 바퀴모드로 변경되어서 Goal position 제어가 되지 않으니 주의하세요.
   ![opencm9.04_dynamixel9.png](/assets/images/sw/opencm/opencm9.04_dynamixel9.png)
   ```
   Dxl.writeWord(1, 8, 0x200);
   if( Dxl.getResult() == COMM_RXSUCCESS ){ // 통신 성공 여부 체크…}
   ```
9. 동작전압을 10V ~ 17V로 설정합니다.
   10V의 데이터는 100(0x64), 17V는 170(0xAA) 이므로 각각 writeByte() 메소드를 통해 하한, 상한을 기록합니다.
   컨트롤 테이블 주소는 각각 하한 범위 전압 = 12(0x0C), 상한 범위 전압 = 13(0x0D) 입니다.
   ![opencm9.04_dynamixel10.png](/assets/images/sw/opencm/opencm9.04_dynamixel10.png)
   ```
   Dxl.writeByte(1, 12, 100);
   Dxl.writeByte(1, 13, 170);

   if( Dxl.getResult() == COMM_RXSUCCESS ){ // 통신 성공 여부 체크…}
   ```
10. 토크를 최대값의 50%만 발휘하도록 합니다.
    MAX Torque 값을 최대값인 0x3FF의 50%인 0x1FF로 설정합니다. Max Torque 하위 바이트 주소 14(0x0E)에 writeByte()이용해 데이터를 씁니다.
    ![opencm9.04_dynamixel11.png](/assets/images/sw/opencm/opencm9.04_dynamixel11.png)
    <br/>
    ```
    Dxl.writeByte(1, 14, 0x1FF);   
    if( Dxl.getResult() == COMM_RXSUCCESS ){ // 통신 성공 여부 체크…}
    ```
    전원을 off 한 뒤 다시 전원을 공급해야만 Max Torque가 변경됩니다.
11. 57RPM의 속도로 Position 180도에 위치시킵니다.
    ```
    Moving Speed( Address 32(0x20) ) = 512(0x200)
    Goal Position( Address 30(0x1E) ) = 512 (0x200)
    ```
    로 설정합니다. 아래와 같이 word단위 데이터로 접근합니다.
    ```
    Dxl.writeWord(1, 32, 512);  // 57 RPM의 속도 설정
    Dxl.writeWord(1, 30, 512);   // 180도 위치로 이동

    if( Dxl.getResult() == COMM_RXSUCCESS ){ // 통신 성공 여부 체크…}
    ```
12. ID가 0인 AX-12는 위치0도에 ID가 1인 AX-12는 위치 300도에 위치시킵니다.(단 두 개의 AX-12 를 똑같은 시점에 출발)
    Syncwrite와 마찬가지로 직접 setTxPacketXXX() 메소드를 활용해서 Packet을 만듭니다. 이 경우 INST_REG_WRITE와 INST_ACTION을 이용해서 Packet을 만들어 봅니다.
    참고로 위치 0도는 0에 해당하고 300도는 1023(0x3FF)에 해당합니다.
    ```
    ID=0, Instruction = INST_REG_WRITE, Address = 30(0x1E), Data = 0
    ID=1, Instruction = INST_REG_WRITE, Address = 30(0x1E), Data = 1023

    Dxl.setTxPacketId(0); // 0번 ID 제어를 명시합니다.
    Dxl.setTxPacketInstruction(INST_REG_WRITE);
    Dxl.setTxPacketParameter(0, 30); // Goal Position Address
    Dxl.setTxPacketParameter(1, Dxl.getLowByte(0)); // Low Byte
    Dxl.setTxPacketParameter(2, Dxl.getHighByte(0)); // High Byte
    Dxl.setTxPacketLength(5);  //전체 데이터 길이 = 데이터 길이 + 3
    Dxl.txrxPacket();

    if( Dxl.getResult() == COMM_RXSUCCESS ){ // 통신 성공 여부 체크…}
    ```
    ![opencm9.04_dynamixel12.png](/assets/images/sw/opencm/opencm9.04_dynamixel12.png)
    <br/>
    두 번째 다이나믹셀에 대한 패킷 전송
    ```
    Dxl.setTxPacketId(1);
    Dxl.setTxPacketInstruction(INST_REG_WRITE);
    Dxl.setTxPacketParameter(0, 30); // Goal Position Address
    Dxl.setTxPacketParameter(1,Dxl.getLowByte(1023)); //Low Byte
    Dxl.setTxPacketParameter(2, Dxl.getHighByte(1023)); //High Byte
    Dxl.setPacketLength(5);
    Dxl.txrxPacket();

    if( Dxl.getResult() == COMM_RXSUCCESS ){ // 통신 성공 여부 체크…
    ```
    <br/>

    ![opencm9.04_dynamixel13.png](/assets/images/sw/opencm/opencm9.04_dynamixel13.png)

    <br />
    0번과 1번 다이나믹셀의 레지스터에 대기중인 Instruction을 바로 실행하려면 INST_ACTION  Packet을 전송합니다.

    ```
    Dxl.setTxPacketId(BROADCAST_ID);
    Dxl.setTxPacketInstruction(INST_ACTION);
    Dxl.setTxPacketLength(2);
    Dxl.txrxPacket();    
    if( Dxl.getResult() == COMM_RXSUCCESS ){ // 통신 성공 여부 체크…}
    ```

    ![opencm9.04_dynamixel14.png](/assets/images/sw/opencm/opencm9.04_dynamixel14.png)
    <br/>
    각각 Packet을 만들어서 전송할 때마다 통신 성공 여부를 체크하는 것이 좋습니다.
