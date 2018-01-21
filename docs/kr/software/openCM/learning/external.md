# 외부 인터럽트

7번핀에 입력되는 신호가 변할 때 LED를 껏다 켜는 코드를 만들어 봅니다. 아래와 같이 3.3V와 연결된 스위치를 7번핀과 연결합니다.
외부 풀다운회로 없이 내부 입력 풀다운 옵션을 활용합니다. 그리고 LED와 저항을 마찬가지로 3.3V와 연결하고 포트는 13번에 연결합니다. LED방향에 주의합니다.
![opencm9.04_interruption1.jpg](/assets/images/sw/opencm/opencm9.04_interruption1.jpg)
![opencm9.04_interruption2.jpg](/assets/images/sw/opencm/opencm9.04_interruption2.jpg)
전역변수 하나로 플래그를 만들어서 7번핀의 신호가 변할 때 마다 인터럽트 루틴에서 플래그를 토글시키는 방법을 응용합니다.
```
volatile int state = LOW;
```
setup()에서 외부 인터럽트는 attachInterrupt() 함수로 설정하고 관련된 핀 7번은 pinMode에서 INPUT_PULLDOWN으로 선언합니다.
```
pinMode(7, INPUT_PULLDOWN);
attachInterrupt(7, LedChange, CHANGE);
```
LedChange ()를 구현합니다. void LedChange (void) 타입으로 구현합니다.
```
void LedChange (){
  if(state == HIGH)
  state = LOW;
  else  
  state= HIGH;
}  
loop(){  
  digitalWrite(BOARD_LED_PIN, state);
}  
```
전체 소스는 아래와 같습니다.
![opencm9.04_interruption3.png](/assets/images/sw/opencm/opencm9.04_interruption3.png)
