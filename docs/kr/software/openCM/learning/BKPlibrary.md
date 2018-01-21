# BKP Library

BKP메모리는 전원이 계속 유지 된 상태에서는 항상 데이터를 유지하기 때문에 사용자 데이터나 중요 데이터를 임시로 저장해서 리셋 복귀 후에 다시 데이터를 참조할 때 유용하게 사용할 수 있다.
OpenCM 보드에서는 외부 라이브러리로 BKP메모리에 대한 API를 제공한다. 아래와 같이 파일 -> 예제 ->  BKP -> ReadWrite 를 선택한다.
![img](/assets/images/sw/opencm/opencm9.04_bkp1.jpg)
예제를 선택하면 아래와 같은 코드가 나타납니다.
![img](/assets/images/sw/opencm/opencm9.04_bkp2.jpg)

## 예제 설명
setup()에서 BKP 메모리를 초기화 하고 Serial2 장치를 57600bps로 초기화 합니다. 그리고 “Start OpenCM9.04 BKP Memory Test”를 Serial2를 통해 출력하고 loop()를 시작합니다.
OpenCM의 STM32F103CB는 16bit 레지스터가 총 10개인 BKP 메모리로 구성되어 있습니다.
loop()에서는 1초 주기로 주소 1에서 10까지 데이터를 출력하다가 Serial2에 어떤 데이터가 들어오
면 BKP메모리의 주소 1부터 10까지 데이터를 기록합니다.
```
#include "BKP.h"
BKP BKP_MEMORY;
int i;
void setup(){
/* Initialize clock and registers for BKP*/

BKP_MEMORY.begin();
Serial2.begin(57600);
Serial2.println("Start OpenCM9.04 BKP Memory Test");
}
void loop(){
 delay(1000);
 for(i=1; i<11;i++){
   Serial2.print("BKP Memory Read = ");
   Serial2.println(BKP_MEMORY.read(i));
 }
 if(Serial2.available()){    
   BKP_MEMORY.enable();
   for(i=1; i<11;i++){
​     BKP_MEMORY.write(i,i*10);
   }    
   BKP_MEMORY.disable();
 }
}
```
BKP메모리의 중요한 특성은 리셋을 눌러서 CPU가 다시 시작해도 BKP메모리 값은 그대로 유지합니다.
그러나 전원을 뽑았다가 다시 꽂으면 데이터가 사라집니다. 아래는 그 출력값을 통해 BKP메모리의 특성을 살펴볼 수 있습니다.
![img](/assets/images/sw/opencm/opencm9.04_bkp3.jpg)
![img](/assets/images/sw/opencm/opencm9.04_bkp4.jpg)
![img](/assets/images/sw/opencm/opencm9.04_bkp5.jpg)
