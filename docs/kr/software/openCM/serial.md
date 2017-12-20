# 시리얼 통신

   OpenCM9.04는 총 4개의 시리얼 장치가 있습니다. Serial1, Serial2, Serial3, SerialUSB가 있고 Serial1은 다이나믹셀 통신포트 전용으로 할당되어 있어서 사용상의 제한이 따릅니다.
   BT-210, BT-110A 같은 4핀 포트를 가진 블루투스 장치를 Serial2를 통해 사용할 수 있습니다. Serial3은 TX3(24), RX3(25)으로 PCB 뒷면에 표시되어 있습니다.

   ![opencm9.04_serial1.jpg](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_serial1.jpg)

   <Serial3 위치>

   SerialUSB는 OpenCM9.04에서 매우 중요합니다. ROBOTIS OpenCM에서 펌웨어 다운로드를 수행하고 Serial1,2,3 장치처럼 데이터 통신도 수행합니다. 사용법은 Serial1,2,3과 거의 동일합니다.

   1. 시리얼 장치를 이용해서 데이터를 전송합니다.
      아래와 같이 4핀 통신포트에 LN-101을 이용해 PC와 연결합니다. PC에는 RoboPlus Terminal이나 시리얼 모니터를 이용해서 COM포트를 오픈합니다.
      ![opencm9.04_serial2.jpg](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_serial2.jpg)
      반드시 아래와 같이 Serial2 장치에 대한 초기화를 수행한 뒤에 loop()에서 아래의 예제를 수행합니다.
      ```
      void setup(){
        Serial2.begin(57600);
      }
      void loop(){
        //테스트 예제 코드
      }
      ```
      데이터 전송은 print()와 println() 메소드를 통해 전송하고 print()메소드는 줄바꿈이 없는 출력을 의미하고 println()은 줄바꿈이 있는 출력을 수행합니다.
      ```
      Serial2.print(“Hello World This is OpenCM9.04”);
      “Hello World” 스트링을 Serial2(TX2, RX2)장치를 통해 출력합니다.
      Serial2.print(“OpenCM9.04 is the first product of OpenCM Series”);
      Serial2.println(“ println() ends this line”);
      Seirla2.println(“This is new line”);
      ```
      println()은 줄바꿈을 하고 새로운 라인으로 출력을 수행합니다.
      아래와 같은 출력을 확인할 수 있습니다.
      ![opencm9.04_serial3.png](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_serial3.png)
      ```
      Serial2.print(12);
      ```
      10진수 12를 출력합니다.
      ```
      int abc = 128;
      Seial2.print(abc);
      ```
      abc변수의 값 128을 출력합니다.
      ```
      Serial2.print(abc, 16);
      ```
      abc변수의 값 128을 16진수 출력합니다. 0x80이 출력됩니다.
      ```
      Serial2.print(abc, 2);
      ```
      abc변수의 값 128을 2진수 출력을 합니다. 마찬가지로 8진수는 두 번째 인자에 8을 지정하면 되고 두 번째 인자가 없으면 기본적으로 10진수를 출력합니다.
      ```
      Serial2.println(3.14);
      ```
      소수점(double) 타입의 3.14를 출력하고 줄바꿈 합니다. 소수점 2자리까지 출력합니다.
      double 변수를 선언해서 출력할 수도 있습니다.
      ```
      double  var = 1.234;
      Serial2.println(var);
      ```
      핀0번, 1번, 2번에서 읽은 아날로그 입력값을 Serial2를 통해 차례로 출력해봅니다.
      여러 개의 print()와 println()을 이용하면 아래와 같이 보기 좋게 출력할 수 있습니다.
      ```
      int sensorValue0=0;
      int sensorValue1=0;
      int sensorValue2=0;
      sensorValue0 = analogRead(0);
      sensorValue1 = analogRead(1);
      sensorValue2 = analogRead(2);
      Serial2.print(“Sensor0 = “); Serial2.print(sensorValue0);
      Serial2.print(“ Sensor1 = “); Serial2.print(sensorValue1);
      Serial2.print(“ Sensor2 = “); Serial2.println(sensorValue2);
      ```
      마지막 sensorValue2 출력만 println()메소드를 이용해서 줄바꿈하면 3개의 아날로그 입력에 대한 깔끔한 출력을 얻을 수 있습니다.
      ![opencm9.04_serial4.png](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_serial4.png)
   2. 시리얼 장치를 이용해 데이터를 받습니다.
      시리얼 장치로 Echo 기능을 구현해 봅니다.
      char형 변수 temp를 통해 Serial2장치에 데이터가 오면 read()메소드로 데이터를 저장하고 바로 print() 메소드로 출력하면 Echo 기능이 구현 됩니다.
      ```
      char temp = 0;
      loop(){
        if ( Serial2.available() ){
        temp = Serial2.read();
        Serial2.print(temp);
        }  
      }  
      ```
      전체 소스는 아래와 같습니다.
      ```
      void setup(){
        Serial2.begin(57600);
      }
      byte temp = 0;  

      void loop(){
      if ( Serial2.available() ){
        temp = Serial2.read();
        Serial2.print(temp);
        }
      }
      ```
      아래와 같이 인터럽트 방식으로 구현해 봅니다.
      Serial장치의 인터럽트는 아래와 같이 반환형이 없고 byte형 인자가 하나 있는 함수를 구현합니다. 여기서 바로 print()메소드로 넘어오는 데이터를 출력하면 Echo 기능이 됩니다.
      따로 프로토타입 선언 없이 아무 위치에나 구현해서 사용합니다.
      ```
      void serialInterrupt(byte buffer){  
      Serial2.print(buffer);
      }  
      ```
      이렇게 구현한 serialInterrupt()를 함수 포인터 형태로setup() 내에서 attachInterrupt()를 통해 설정해 줍니다.
      ```
      Serial2.attachInterrupt(serialInterrupt);   
      ```
      인터럽트를 활용한 Serial2 장치의 데이터 입력에 대한 전체 코드는 아래와 같습니다.
      ```
      void setup(){
        Serial2.begin(57600);
        Serial2.attachInterrupt(serialInterrupt);
      }

      void serialInterrupt(byte buffer){  
        Serial2.print(buffer);
      }  

      void loop(){
        //코드가 없어도 됩니다.
      }
      ```
   3. SerialUSB 장치를 이용해 데이터를 출력합니다.
      아래와 같이 OpenCM9.04의 Micro-B USB 커넥터를 이용해서 바로 PC와 연결합니다.
      이번 예제는 LN-101과 같인 장치 없이 OpenCM9.04만으로 PC와 데이터 통신을 수행합니다.
      ![opencm9.04_serial5.jpg](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_serial5.jpg)
      아래와 같이 SerialUSB 장치에 대한 초기화를 수행한 뒤에 loop()에서 아래의 예제를 수행합니다. Baud rate에 대한 지정은 없습니다.
      ```
      void setup(){
        SerialUSB.begin();
      }

      void loop(){
      //테스트 예제 코드
      }
      ```
      Serial 장치와 사용법이 거의 같습니다. print(), println()메소드를 통해 같은 방식으로 제어 하면 됩니다.
      ```
      SerialUSB.print(“CM-900 is the first product of CM-9 Series”);  
      SerialUSB.println(“ println() ends this line”);  
      SeirlaUSB.println(“This is new line”);  
      ```
      10진수 12를 출력해봅니다.
      ```
      SerialUSB.print(12);  
      ```
      int형 변수를 통해 출력해봅니다.
      ```
      int abc = 128;  
      SerialUSB.print(abc);  
      ```
      이번엔 abc 변수의 값을 16진수로 출력합니다.
      ```
      SerialUSB.print(abc, 16);  
      ```
      abc변수의 값 128이 16진수 형태인 0x80이 출력됩니다.
      ```
      SerialUSB.print(abc, 2);  
      ```
      abc변수의 값 128을 2진수 출력을 합니다. 마찬가지로 8진수는 두 번째 인자에 8을 지정하면 되고 두 번째 인자가 없으면 기본적으로 10진수를 출력합니다.
      ```
      SerialUSB.println(3.14);  
      ```
      소수점(double) 타입의 3.14를 출력하고 줄바꿈 합니다. 소수점 2자리까지 출력합니다.
      double 변수를 선언해서 출력해 봅니다.
      ```
      double  var = 1.234;  
      SerialUSB.println(var);  
      ```
   4. 시리얼 USB장치를 이용해 데이터를 입력 받습니다.
      시리얼 USB 장치로 Echo 기능을 구현해 봅니다.
      char형 변수 temp를 통해 Serial USB장치에 데이터가 오면 read()메소드로 데이터를 저장하고 바로 print() 메소드로 출력하면 Echo 기능이 구현 됩니다
      ```
      char temp = 0;  
      loop(){  
        if ( SerialUSB.available() ){  
        temp = SerialUSB.read();
        SerialUSB.print(temp);
        }  
      }  
      ```
      전체 소스는 아래와 같습니다.
      ```
      void setup(){
        SerialUSB.begin();
      }

      byte temp = 0;  
      void loop(){

      if ( SerialUSB.available() ){
        temp = SerialUSB.read();
        SerialUSB.print(temp);
        }
      }
      ```

      아래와 같이 인터럽트 방식으로 구현해 봅니다.
      Serial USB의 인터럽트는 아래와 같이 반환형이 없고 byte형 인자와 byte* 인자가 있는 함수로 구현합니다. 여기서 바로 print() 메소드로 넘어오는 데이터를 출력하면 Echo 기능이 됩니다.
      PC의 터미널로 USB COM 포트에 데이터를 쓰면 1바이트 씩 전송되기 때문에 nCount =1이고 buffer 의 index 0번 데이터만 Echo하면 충분합니다.
      ```
      void usbInterrupt(byte nCount, byte* buffer){
      SerialUSB.print(buffer[0]);
      }
      ```
      이렇게 구현한 usbInterrupt()를 함수 포인터 형태로setup() 내에서 attachInterrupt()를 통해 설정해 줍니다.
      ```
      SerialUSB.attachInterrupt(usbInterrupt);
      ```
      loop()함수는 아래와 같이 빈 함수로 두어도 괜찮습니다.
      ```
      void loop(){
      }
      ```
      SerialUSB 장치의 인터럽트 활용한 전체 코드는 아래와 같습니다.
      ```
      void setup(){
        SerialUSB.begin();
        SerialUSB.attachInterrupt(usbInterrupt);
      }

      void usbInterrupt (byte nCount, byte* buffer){  
      SerialUSB.print(buffer[0]);
      }  

      void loop(){
      //코드가 없어도 됩니다.
      }
      ```
