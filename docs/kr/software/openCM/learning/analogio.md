## 아날로그 IO 입출력

아날로그 입력은 반드시 OpenCM9.04 실크스크린의 ANALOG IN 영역에 위치한 0번~9번핀만 아날로그 입력이 됩니다.
아날로그 출력은 TIMER를 활용한 PWM출력을 통해 아날로그 출력을 대신합니다.

![opencm9.04_analog1.jpg](/assets/images/sw/opencm/opencm9.04_analog1.jpg)

1. 핀3번에 가변저항으로 아날로그 입력을 받습니다.
   아래와 같이 3번핀에 가변저항을 연결하고 전압은 3.3V를 연결합니다.
   ![opencm9.04_analog2.jpg](/assets/images/sw/opencm/opencm9.04_analog2.jpg)
   ![opencm9.04_analog3.jpg](/assets/images/sw/opencm/opencm9.04_analog3.jpg)
   3번 핀의 아날로그 입력을 위해서는 pinMode(3, INPUT_ANALOG)를 통해 아날로그 입력으로 핀모드 설정을 해주시면 준비는 끝납니다.
   설정된 3핀으로 아날로그 값을 읽기 위해서는 analogRead()를 사용합니다.
   ```
   int value = analogRead(3);
   ```
   // 0번 핀에서 아날로그 입력받아서 value 변수에 할당합니다.
   여기서 value에 할당되는 값은 12bit ADC 값으로 0~ 4095값이 됩니다.
   전체 코드를 통해 읽은 ADC값을 출력해봅니다.
   ```
   void setup(){
     pinMode(3, INPUT_ANALOG);  
   }
   void loop(){
     int value = analogRead(3);
     SerialUSB.println(value);   // value값을 출력합니다.
     delay(100); //delay time for USB transfer
   }
   ```
2. 핀6번에 아날로그 출력(PWM)을 합니다.
   핀 6번에서 출력되는 PWM을 이용해서 LED를 제어합니다. 아래와 같이 브레드 보드를 이용해서 LED와 저항을 연결하고 핀6과 연결합니다.
   ![opencm9.04_analog4.jpg](/assets/images/sw/opencm/opencm9.04_analog4.jpg)
   ![opencm9.04_analog5.jpg](/assets/images/sw/opencm/opencm9.04_analog5.jpg)
   6번 핀의 아날로그 pinMode(6, PWM)으로 설정합니다.
   설정된 6번핀을 통해 PWM 출력은 analogWrite()를 이용합니다.
   analogWrite(6, 10000);
   PWM출력을 통해 아날로그 출력을 대신합니다. PWM의 Duty cycle은 두 번째 인자를 통해 제어합니다. 여기서는 10000이지만 0~ 65535 범위의 값으로 듀티 사이클을 지정할 수 있습니다.
   0이면 0% 듀티 사이클이고 65535일 경우 100%듀티 사이클을 나타냅니다.
   ![opencm9.04_analog6.jpg](/assets/images/sw/opencm/opencm9.04_analog6.jpg)
   전체 코드를 확인합니다.
   ```
   void setup(){
     pinMode(6, PWM);
   }  
   void loop(){
   for(int i=1; i < 7; i++){
   ​      analogWrite(6, i*10000);//generate pwm as 10000 ~ 60000 scale
   ​      delay(100);
    }
   }   
   ```
   analogWrite()의 두번째 인자를 통해 아래와 같은 다양한 Duty Cycle의 PWM을 구현할 수 있습니다.
3. Status LED를 천천히 꺼지도록 Dimming 시켜봅니다.
   Status LED는 핀 14번과 연결되어 있고 핀 14번 역시 PWM 출력이 가능합니다. 파일 --> 예제 --> 01. Basic --> f_Led_Fadin을 오픈 합니다.
   ![opencm9.04_analog7.jpg](/assets/images/sw/opencm/opencm9.04_analog7.jpg)
   OpenCM9.04에 다운로드 해보면 Status LED가 반복적으로 천천히 켜졌다가 꺼지는 동작을 합니다.
   ![img](/assets/images/sw/opencm/opencm9.04_analog8.png)
