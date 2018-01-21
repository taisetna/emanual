## 디지털IO 입출력

1. 핀13번에 LED 연결해봅니다.
   아래와 같이 OpenCM9.04에 LED와 저항을 연결합니다. 포트는 13번에 연결합니다.
   ![opencm9.04_digita1.jpg](/assets/images/sw/opencm/opencm9.04_digita1.jpg)
   디지털 출력을 위해서는 반드시 setup()에서 pinMode(13, OUTPUT)을 통해 13번 핀을 OUTPUT으로 설정합니다.
   그리고 digitalWrite()함수로 HIGH/LOW  값을 지정합니다.
   digitalWrite(13, HIGH); //13번핀에 HIGH를 출력합니다.
   digitalWrite(13,LOW); //13번핀에 LOW를 출력합니다.
   핀 13번이 LOW일 때 GND(-극)이 되어서 전류가 흐르기 때문에 LED가 켜집니다. 반드로 HIGH가 핀13번이 3.3V가 되어서 전류가 흐를수 없기 때문에 LED가 꺼집니다.
   이러한 원리로 LED가 깜빡이는 스케치 코드를 작성합니다.
   ```
   void setup(){
     pinMode(13, OUTPUT);
   }

   void loop(){
     digitalWrite(13, HIGH);
     delay(100); //0.1 초 지연
     delay(100); //0.1 초 지연
     delay(100); //0.1 초 지연
   }
   ```
   0.1초 마다 깜빡거리는 LED를 확인하실 수 있습니다.
2. Status LED를 깜박이게 만들어 봅시다.
   OpenCM9.04에는 위의 예제처럼 LED를 연결하지 않고도 보드에 내장된 녹색의 Status LED를 가지고 테스트할 수 있습니다.
   ![opencm9.04_digita2.jpg](/assets/images/sw/opencm/opencm9.04_digita2.jpg)
   ​                       <Status LED 위치>
   Status LED는 핀 14번과 연결되어 있고 미리 선언된 BOARD_LED_PIN을 사용해서 제어할 수 있습니다.
   BOARD_LED_PIN을 가지고 스케치 코드를 작성하면 보드가 바뀌어도 코드를 수정할 필요가 없는 장점이 있습니다.
   파일 --> 예제 --> Basic --> b_Blink 예제를 오픈합니다.
   ![opencm9.04_digita9.png](/assets/images/sw/opencm/opencm9.04_digita9.png)
   다운로드 하면 녹색의 Status LED가 깜박입니다.
3. 핀7번에 디지털 입력을 받아봅니다.
   아래와 같이 버튼과 풀다운 저항을 연결합니다. 포트는 7번을 이용해서 디지털 입력을 받습니다.
   ![opencm9.04_digita3.jpg](/assets/images/sw/opencm/opencm9.04_digita3.jpg)
   ​                       <풀다운 회로로 구성된 버튼 연결>
   OpenCM9.04의 IO핀에 디지털 입력을 위해서는 반드시 setup()에서 pinMode(7, INPUT)을 통해 7번 핀을 INPUT으로 설정이 필요합니다.
   그리고 아래와 같이 digitalRead() 함수로 HIGH/LOW 값을 받습니다.
   int value = digitalRead(7); // 7번핀을 읽어서 value변수에 할당함
   전체 코드를 통해 확인합니다. 버튼이 눌리면 HIGH가 감지되고 스위치가 떨어지면 LOW가 감지됩니다.
   버튼이 떨어졌을 때 LOW가 감지되는 것은 풀다운 저항과 연결된 GND가 있기 때문입니다.
   ```
   void setup(){   
     pinMode(7, INPUT);
     SerialUSB.begin();
   }  
   void loop(){  
     int value = digitalRead(7);
     if ( value == HIGH)
      SerialUSB.println(“HIGH Detected!”);
     else
      SerialUSB.println(“LOW Detected!”);
     delay(100);  
   }  
   ```  
   위의 회로를 아래와 같이 풀업 회로로 변경하면 반대로 동작합니다. 버튼이 눌러지면 LOW가 감지되고 떨어지면 HIGH가 감지됩니다.
   버튼이 떨어졌을 때 HIGH가 감지되는 것은 풀업 저항과 연결된 3.3V전압이 때문입니다.
   ![opencm9.04_digita4.jpg](/assets/images/sw/opencm/opencm9.04_digita4.jpg)
   ​                             <풀업 회로로 구성된 버튼 연결>
4. D. 풀업, 풀다운 저항 없이 디지털 입력을 받아 봅시다.
   OpenCM9.04는 디지털 입력에서 풀다운이나 풀업 저항이 없이 스위치 회로 구성이 가능합니다.
   OpenCM9.04의 26개 GPIO핀들은 내부적으로 입력 Pull-up/Pull-down 저항을 가지고 있고 소프트웨어적으로 설정할 수 있습니다.
   만약 내부 풀업이 필요하면 pinMode(7, INPUT_PULLUP)으로 설정하시고 풀다운 회로가 필요하면 pinMode(7, INPUT_PULLDOWN)으로 합니다.
   INPUT으로 선언하면 플로팅 된 디지털 입력을 의미하기 때문에 외부에 풀업이나 풀다운 회로가 있어야 합니다. 예를 들어 봅시다.
   아래 회로는 핀 7을 통해 디지털 입력을 받는 회로인데 버튼이 바로 GND와 연결됩니다. 이런 경우 7번핀을 INPUT_PULLUP으로 선언하면 정상적으로 버튼이 동작하게 됩니다.
   ![opencm9.04_digita5.jpg](/assets/images/sw/opencm/opencm9.04_digita5.jpg)
   이 경우 버튼이 눌리면 LOW가 감지되고 떨어지면 내부 풀업에 의해 HIGH가 감지됩니다.
   void setup(){   
   pinMode(7, INPUT_PULLUP);
   SerialUSB.begin();
   }  
   void loop(){  
   int value = digitalRead(7);
   if ( value == HIGH)
   SerialUSB.println(“HIGH Detected!”);
   else
   SerialUSB.println(“LOW Detected!”);
   delay(100);  
   }
   반대의 경우 아래 연결도처럼 버튼을 3.3V에 바로 연결합니다.
   ![opencm9.04_digita6.jpg](/assets/images/sw/opencm/opencm9.04_digita6.jpg)
   이 경우 버튼이 눌러지면 HIGH가 감지되고 떨어지면 내부 풀다운에 의해 LOW가 감지됩니다.
   ```
   void setup(){   
     pinMode(7, INPUT_PULLDOWN);
     SerialUSB.begin();
   }  
   void loop(){  
     int value = digitalRead(7);
     if ( value == HIGH)
      SerialUSB.println(“HIGH Detected!”);
     else
      SerialUSB.println(“LOW Detected!”);
     delay(100);  
   }
   ```
5.  User Button을 이용해서 입력 받아 봅시다.
   버튼도 Status LED처럼 내장된 User Button을 가지고 따로 버튼 회로를 만들 필요가 없이 사용할 수 있습니다.
   회로도를 보면 내장된 풀다운 입력을 사용하는 것을 알 수 있습니다.
   ![opencm9.04_digita7.jpg](/assets/images/sw/opencm/opencm9.04_digita7.jpg)
6. User Button은 23번 핀으로 연결되어 있으므로 23번핀을 직접 지정해도 되고 BOARD_BUTTON_PIN을 써도 됩니다.
```
   void setup(){   
     pinMode(BOARD_BUTTON_PIN, INPUT_PULLDOWN);
     SerialUSB.begin();
   }  
   void loop(){  
     int value = digitalRead(BOARD_BUTTON_PIN);
     if ( value == HIGH)
      SerialUSB.println(“HIGH Detected!”);
     else
      SerialUSB.println(“LOW Detected!”);
     delay(100);  
   }
   ```
   다운로드 해보면 유저 버튼이 눌리면 HIGH가 입력되고 떨어지면 내부 풀다운 회로에 의해서 LOW가 입력됩니다.
7. Status LED를 토글 시켜봅니다.
   1번 핀의 현재 출력이 HIGH이면 LOW가 되고, LOW이면 HIGH로 반전 시킵니다.
   digitalWrite(1, HIGH); // 1번핀이 HIGH가 됩니다.
   togglePin(1); // HIGH 상태였던 1번핀이 다시 LOW가 됩니다.
   이러한 원리로 LED Blink 예제를 매우 간단하게 작성할 수 있습니다. 간단히 Status LED 를 가지고 togglePin()을 사용해 봅니다.
   ```
   void setup(){   
     pinMode(BOARD_LED_PIN, OUTPUT);
   }  
   void loop(){   
     togglePin(BOARD_LED_PIN);
     delay(100); //0.1 초 지연
   }
   ```
   0.1초 간격으로 LED가 깜빡입니다. 참고로 BOARD_LED_PIN만 토글하는 toggleLED()를 써도 같은 동작을 수행합니다.
   ![opencm9.04_digita8.png](/assets/images/sw/opencm/opencm9.04_digita8.png)
