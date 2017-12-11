# Zig2Serial

로보 플러스 매니저에서 Zig2Serial을 이용하여 Zig-100모듈을 관리할 수 있습니다. 관리 방법은 다음과 같습니다.

1. 먼저 Zig2Serial에 Zig-100을 장착한 후, PC의 시리얼 포트를 Zig2Serial과 연결합니다.
   ([Zig2Serial - Zig100 연결하기])

    다음 그림과 같이 시리얼 포트가 없는 경우 USB2Dynamixel을 이용할 수 있습니다.

   ![img](/assets/images/sw/rplus1/manager/zig2serial_u2d.png)
2. Zig2Serial이 연결된 포트를 선택하고 Zig2Serial 관리 아이콘을 클릭합니다.
   (제어기와 달리 자동 찾기가 되지 않습니다.)

     ![img](/assets/images/sw/rplus1/manager/zig2serial_inite.png)
3. Zig2Serial 관리 아이콘을 클릭하면 다음과 같은 화면을 볼 수 있습니다. "Zigbee 설정" 버튼을 클릭합니다.

     ![img](/assets/images/sw/rplus1/manager/zig2serial_manage.png)
4. OK버튼을 누른 후 3초 이내에 리셋 버튼을 누르십시오.

     ![img](/assets/images/sw/rplus1/manager/zig2serial_connection.png)
5. Zigbee모듈이 정상적으로 인식되면 다음과 같은 화면을 볼 수 있으며, 기능을 설정할 수 있습니다.
   - 현재 내 ID와 상대 ID를 확인할 수 있습니다.
   - 상대 ID를 바꿀 수 있습니다.
   - Broadcast 모드를 설정할 수 있습니다.
   - Wait 모드를 설정할 수 있습니다.

     ![img](/assets/images/sw/rplus1/manager/zig2serial_setting.png)
6. 만약 Zig100모듈을 찾지 못한 경우, 모듈이 정상적으로 연결되었는지 확인 해 보십시오.

     ![img](/assets/images/sw/rplus1/manager/zig2serial_connection_fail.png)

- 다른 무선 통신 모듈과 데이터를 주고 받을 수 있으며, RC-100 리모컨 신호를 생성 및 전송할 수 있습니다.

## 관련동영상

 무선통신 모듈 지그비 설정하기
 <iframe width="640" height="360" src="https://www.youtube.com/embed/YgebCObXJZg" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>

[Zig2Serial - Zig100 연결하기]: ???
