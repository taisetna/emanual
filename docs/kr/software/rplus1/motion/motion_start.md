# 시작하기

## 로봇 모션과 파일 모션

### 로봇 모션

로봇 모션은 제어기 안에 존재하는 모션 데이터를 의미합니다.

로봇 모션 창은 이 데이터를 보여주고, 편집할 수 있도록 합니다.

로봇 모션 창은 로봇을 연결해야만 나타납니다. ([로봇 연결 방법] 보기)

![img](/assets/images/sw/rplus1/motion/rmfm_robotmotion.png)

### 파일 모션

파일 모션은 PC에 파일로 존재하는 모션 데이터를 의미합니다.

파일 모션 창은 이 데이터를 보여주고 편집할 수 있도록 합니다.

파일 모션 창은 여러 개를 띄울 수 있습니다.

![img](/assets/images/sw/rplus1/motion/rmfm_filemotion.png)

## 로봇 연결하기

1. 로봇을 PC와 연결합니다. (연결 방법은 [각 제어기 정보]를 참고하세요.)
2. 통신 포트를 선택합니다.
   로봇이 연결된 통신 포트를 선택합니다. 만약, 통신 포트를 모른다면 자동 찾기를 선택합니다.

   ![img](/assets/images/sw/rplus1/motion/conn_portselection.png)
3. 로봇에 연결합니다.
   연결 메뉴를 선택합니다.

   ![img](/assets/images/sw/rplus1/motion/conn_connecticon.png)

   ![img](/assets/images/sw/rplus1/motion/conn_connectmenu.png)

   로봇에 연결하지 못하면 다음과 같은 문제를 확인하기 바랍니다.
   - 제어기를 PC에 연결했습니까?
   - 제어기 전원을 켰습니까?
   - 제어기가 연결된 올바른 포트를 선택했습니까?
   - RoboPlus Motion을 사용할 수 있는 제어기입니까?
     - CM-100의 경우는 사용할 수 없습니다.
     - CM-5의 경우는 펌웨어 업그레이드를 해야 사용할 수 있습니다.
4. 로봇의 연결을 끊습니다.
   로봇의 연결을 끊으려면 해제 메뉴를 선택하거나 로봇 모션 창을 닫습니다.

   ![img](/assets/images/sw/rplus1/motion/conn_disconnecticon.png)

## 모션 다운로드

특정 파일 모션을 로봇 모션으로 바꿀 수 있습니다.

- 다운로드 할 파일 모션을 엽니다.

- 로봇을 연결합니다.

- 다운로드 버튼을 누르고 완료되기를 기다립니다.

 ![img](/assets/images/sw/rplus1/motion/down_menu.png)

- 파일 모션의 내용이 로봇 모션에 옮겨진 것을 확인합니다.

 ![img](/assets/images/sw/rplus1/motion/down_result.png)

### 관련동영상

 로보플러스 프로그램 다운로드(CM-510/530)
<iframe width="560" height="315" src="https://www.youtube.com/embed/dHCqPs1_2yY" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>

## 모션 실행/정지

### 모션 실행

만든 모션을 실행해볼 수 있습니다.

원하는 페이지를 선택한 후, 실행 메뉴를 선택합니다.

![img](/assets/images/sw/rplus1/motion/playstop_motion_play.png)

모션 실행 시도시 다음과 같은 문제가 발생할 수 있습니다.

- 이 경우는 로봇 모션 창에서 작업할 경우 나타납니다.
이 문제는 Next나 Exit로 연결된 페이지가 수정되었고, 제어기 메모리가 작아서 임시로 저장할 수 없기  때문입니다.
![img](/assets/images/sw/rplus1/motion/playstop_motion_robot_play_error.png)
실행하기 전에 저장을 하면 이 문제는 해결이됩니다. 만약, 저장하지 않고 확인을 눌러 진행한다면 현재 페이지만 실행됩니다.

- 이 경우는 파일 모션 창에서 작업할 경우 나타납니다.
제어기가 아닌 PC에 데이터가 있는 경우 제어기 메모리가 작아서 Next나 Exit로 연결된 페이지를 임시로 저장할 수 없기 때문입니다.
![img](/assets/images/sw/rplus1/motion/playstop_motion_file_play_error.png)
오직, 선택한 페이지만 실행 가능합니다. 만약, 연결된 페이지도 실행하려면 다운로드 해야 합니다.

### 모션 정지

실행중인 모션을 정지시킵니다.

![img](/assets/images/sw/rplus1/motion/playstop_motion_stop.png)

모션 정지는 바로 멈추는 것이 아니라 Exit 페이지를 실행한 후 정지합니다.

### 모션 비상 정지

실행중인 모션을 정지시킵니다.

![img](/assets/images/sw/rplus1/motion/playstop_e_stop.png)

모션 정지와 달리 비상 정지는 그 즉시 멈춥니다.

[로봇 연결 방법]: ???
[각 제어기 정보]: ???
