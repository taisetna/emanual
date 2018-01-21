# Sensor Module 사용방법

로보티즈 센서 모듈들은 모두 5핀 포트와 연결될 수 있습니다. 연결 방법은 OpenCM9.04 하드웨어 설명을 참고하시면 됩니다.

참고로 A타입의 경우 5핀 커넥터를 따로 납땜해야 하고 B타입, C타입은 미리 5핀 커넥터가 달려 있습니다.

![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor.jpg)

주의할 점은 5핀에 할당된 핀들이 양쪽 40핀 IO에도 공유가 되어 있으므로 아래 쓰고 있는 포트에 할당된 IO핀은 헤더에서 쓰지 않아야 합니다.

![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor1.jpg)

예를 들면 1번 포트에 IR센서를 연결하면 2번, 6번, 7번핀은 헤더에서 쓸 수 없습니다.

1. [IR센서 모듈]
   1. 연결도
     동작원리는 E-manual에서 처럼 SIG2(MOT+)에 High를 주면 발광 LED가 켜져서 생기는 적외선이 수광 LED에 감지가 되어서 ADC로 나타납니다.
     적외선 센서 모듈은 최대한 SIG2번에 트랜지스터 회로가 있는 포트1, 4번에 연결하세요. 2번, 3번 포트는 ADC값이 작게 나옵니다.
     아래는 포트1번에 연결된 그림입니다. 커넥터 방향은 회색선이 USB쪽으로 연결하시면 됩니다.
     ADC값은 약 10~15us 뒤에 읽으면 최대값을 읽을 수 있습니다. 그리고 거리에 따라 감지할 수 있는 ADC값의 특성이 아래와 같기 때문에 이 점을 잘 고려해서 활용을 해야 합니다.
     최대 15cm 이상 떨어진 물체는 감지할 수 없으며 지나치게 가까운 물체는 적외선이 반사되어 수광부로 들어오는 각도가 맞지 않아서 센서 값이 떨어지는 구간이 생깁니다.
     (0~1.5cm사이 구간에 해당)
   2. 동작 확인
   ​    ROBOTIS OpenCM의 예제 --> 07. Sensors --> IR_Read 를 오픈합니다.
   ​    다운로드 후에 시리얼 모니터를 열고 물체(흰색에서 최대입니다)를 갖다 대면 아래와 같이 ADC값을 볼 수 있습니다.
   ![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor4.png)
   3. 동작 코드
   ​    IR 센서는 SIG2번에 해당하는 핀과 ADC포트만 제어하면 IR센싱을 할 수 있습니다. 올로 라이브러리는 이러한 원리로 미리 코딩이 되어 있습니다.
   ​    ![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor5.png)
      포트1번에 할당된 핀들이 2,6,7번을 확인합니다. setup()에서 SIG1,2번에 해당하는 6,7번 핀을 모두 LOW로 초기화 하고 2번을 아날로그 입력으로 초기화합니다.
      ![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor6.png)
   ​    readIR이라는 함수에서 SIG2(7번핀)에서 HIGH를 주어서 발광LED를 ON하고  15us뒤에 아날로그 값을 읽으면 최적의 ADC값을 읽을 수 있습니다.
      그리고 다시 SIG2번을 LOW로 주면 한 사이클이 끝납니다. 뒤에 30us는 없어도 상관 없습니다.
      참고로 올로 라이브러리는 이와 같은 원리로 미리 코딩이 되어 있으므로 편리하게 이용할 수 있습니다.
2. [DMS 센서 모듈]
   1. 연결도
     기본적으로 5핀중에 가운데 3핀만으로 전압 인가 후 ADC값을 읽어서 간단히 활용합니다.
    적외선 센서와 비교해서 색과 반사율이 변해도, 거리에 따른 출력값 변화가 거의 없는 것이 장점입니다.
     OpenCM9.04의 5핀 센서 포트 중에 아무 포트나 연결해도 무방합니다.
    DMS 센서는 SIG1, 2번을 쓰지 않기 때문에 포트를 가리지 않습니다. 아래는 포트2번에 연결하였고 예제 코드도 2번 포트를 기준으로 설명합니다.
   2. 동작 확인
   파일 --> 예제 --> 07. Sensors 예제 중에 OLLO_DMS_Read 예제를 다운로드 후 시리얼 모니터를 통해 확인 가능합니다.
   ![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor8.jpg)
   3. 동작 코드
   DMS 센서 모듈과 같이 5핀 중에 3핀으로 구성된 센서는 그냥 아날로그 입력 핀만 계속 Read하면 됩니다. 별다른 초기 코드가 필요 없습니다.
   ![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor9.png)
3. [Gyro 센서]
   1. 연결도 및 센서 내부 구조
     로보티즈 자이로 센서도 마찬가지로 OpenCM9.04의 5핀 포트에 연결해서 X, Y 각속도(회전 가속도)를 측정할 수 있습니다.
   ![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor3.png)
   Gyro 센서 모듈을 OpenCM9.04의 5핀 포트 1번, 2번에 각각 연결한다. 아래 연결도처럼 포트1번에 X축 핀을 연결하고 포트2번에 Y축 포트를 연결한다.
   2. 동작 코드
   예제-> 07. Sensors -> OLLO_Gyro_Read 예제를 다운로드 한 뒤 시리얼 모니터를 열면 아래와 같이 X, Y축 회전 가속도 값을 ADC로 확인 할 수 있습니다.
   X축핀이 연결된 포트1번과 Y축핀이 연결된 포트2를 초기화하고 루프에서 60ms 주기로 X, Y축의 회전 가속도를 ADC값으로 읽습니다.
   ![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor13.png)
   DMS 센서 모듈과 동일하게 루프에서 단순히 아날로그 핀값을 읽기만 하면 됩니다.
   ![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor14.jpg)
4. [LED 모듈]
   1. 연결도 및 내부구조
     LED 모듈은 센서 모듈이 아닌 단순히 LED 2개를 디스플레이 형식으로 활용하기 위한 모듈입니다.
     회로도를 보면 MOT+-가 각각 HIGH이면 OFF, LOW이면 ON이되는 Current Sink방식으로 제어를 하고 있음을 알 수 있습니다.
     OpenCM9.04의 5핀 포트 1번, 4번의 SIG2핀은 LOW가 되지 않기 때문에 LED 모듈 사용에 제약이 있으므로 5핀 포트 2번, 3번을 사용하세요. 아래 그림은 포트 3번을 통해 LED 모듈을 연결하였습니다.
   2. 동작 확인
      파일 -> 예제 -> 07. Sensors 예제 중에 OLLO_LED_Blink 를 다운로드 후 실행하면 양쪽 LED가 교대로 깜빡이는 것을 확인할 수 있습니다.
      LED 모듈은 ADC 핀이 필요 없으므로 SIG1, 2번 핀만 활용하면 됩니다. 아래와 같이 setup()에서 포트 3번을 초기화하면 LED 모듈을 사용할 수 있습니다.
   ![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor15.png)
5. [접촉 센서]
   1. 연결도 및 연결도
    <접촉 센서는 그냥 버튼입니다>
     접촉 센서는 간단히 윗부분을 눌렀을 때 버튼처럼 동작해서 접촉 유무를 감지합니다. 그냥 버튼으로 활용해도 괜찮습니다.
     회로도 역시 자주 쓰는 버튼회로에 지나지 않습니다. 버튼을 누르면 HIGH가 인가되고 떼면 LOW가 인가되는 구조입니다.
     연결은 OpenCM9.04의 포트2번에 연결합니다.
   2. 동작 코드
      OLLO 라이브러리의 OLLO_TOUCH_Read를 다운로드 한 뒤 시리얼 모니터를 오픈하면 결과를 확인 할 수 있습니다. 1이면 버튼이 누르지 않은 상태이고 버튼을 누르면 0값이 출력됩니다.
      터치 센서 역시 5핀 중에 가운데 3개의 핀만 활용합니다. ADC 핀은 디지털 입력으로 선언해서 사용하는 것을 추천합니다.
      터치 센서 내부적으로 Pull-down회로가 없기 때문에 Pull-down 옵션으로 INPUT_PULLDOWN을 선언해야 합니다. OLLO라이브러리는 내부적으로 이러한 방식으로 5핀센서의 핀을 초기화합니다.
   ![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor16.png)
   ![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_sensor17.png)

[IR센서 모듈]: ???
[DMS 센서 모듈]: ???
[Gyro 센서]: ???
[LED 모듈]: ???
[접촉 센서]: ???
