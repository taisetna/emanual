---
layout: archive
lang: kr
ref: rplus1_manager
read_time: true
share: true
author_profile: false
permalink: /docs/kr/software/rplus1/manager/
sidebar:
  title: R+ Manager 1.0
  nav: "rplusmanager1"
---

# 로보플러스 매니저(RoboPlus Manager)

로보플러스 매니저는 로봇을 구성하는 각 장치들을 관리해줍니다.
이 프로그램의 주요 역할은 다음과 같습니다.

- 제어기 펌웨어를 관리합니다. [(업데이트 및 복구 기능)]
- 제어기 및 주변 장치들의 상태를 점검합니다. [(테스트 기능)]
- 사용에 필요한 모드 등을 설정할 수 있습니다. (설정 기능)

`Note` 통신이 불안정하다면 전압레벨 차이 일수 있습니다. {: .notice}

`Note` 연결된 장비 및 PC가 그라운드와 연결되어 있는지 확인해주세요.{: .notice}

![img](/assets/images/sw/rplus1/manager/roboplus_manager.png)

# 시작하기

## 제어기 연결

1. 제어기를 PC와 연결합니다. (연결 방법은 각 [제어기 정보]를 참고하세요.)
2. 사용할 통신 포트를 선택합니다.
   자동 찾기 기능을 이용하면 쉽게 통신 포트를 설정할 수 있습니다.
   ![img](/assets/images/sw/rplus1/manager/connection.png)

   만약, 해당 통신 포트가 사용중으로 나타나면 사용중인 프로그램을 찾아 사용을 해제해야 합니다.
   ![img]/(assets/images/sw/rplus1/manager/connection_in_use.png)

   RoboPlus Manager가 제어기를 찾지 못하면 아래와 같은 에러 메시지가 나타납니다.
   ![img](/assets/images/sw/rplus1/manager/connection_not_find.png)

   - PC 와 제어기가 연결되어 있는지 확인합니다. (연결 방법은 각 제어기 정보를 참고하세요.)
   - 제어기의 전원이 켜져 있는지 확인합니다.
   - 제어기가 연결된 통신 포트가 바르게 선택되어 있는지 확인합니다.
3. 관리를 시작합니다. (각 [제어기별 관리방법]을 참고하세요.)

### 제어기 연결 안될시 확인사항

1. 제품을 컴퓨터에 연결시 장치 관리자에게 연결장치(LN101, USB2DXL, 제어기 등)의 포트가 생기는지 확인해주세요.
   ![img](/assets/images/sw/rplus1/manager/manege_controller.jpg)
2. 포트가 잡힐 시
   펌웨어 복구를 시도해보시길 바랍니다. 펌웨어 복구 방법은 E-manual을 참조해 주시길 바랍니다.
   - [펌웨어복구] 바로가기
   - [CM9.04 펌웨어복구] 바로가기
3. 포트가 잡혀도 펌웨어 복구가 안될시
   - 다른 제품이나 위 사항을 확인 후에도 안될시 고객지원으로 연락을 주시거나 A/S 신청을 해주시기 바랍니다.
4. 포트가 안뜰시
 - [CM150, CM200 해결방법]
 - [OpenCM9.04 해결방법]

다른 제품이나 위 사항을 확인 후에도 안될시 고객지원으로 연락을 주시거나 A/S 신청을 해주시기 바랍니다.

# 펌웨어 관리

## 펌웨어 업데이트

펌웨어는 제어기에 설치되어 있는 프로그램을 말하며, tsk 프로그램을 실행하거나 제어기 관리 등의 역할을 담당하고 있습니다.

RoboPlus Manager는 인터넷을 통해 새 버전의 펌웨어를 자동으로 감지하여 항상 최신으로 유지시킵니다.

![img](/assets/images/sw/rplus1/manager/update_2.png)

제어기 펌웨어 업데이트 방법

1. 제어기와 연결되면 자동으로 제어기의 펌웨어를 검색하며 버전이 낮다면 업데이트 여부를 묻습니다.

   ![img](/assets/images/sw/rplus1/manager/update_5.png)
2.  '예(Y)'를 누르면 다음과 같이 제어기 펌웨어 업데이트 마법사를 시작합니다.

   ![img](/assets/images/sw/rplus1/manager/update_6.png)
3. 현재 연결된 제어기의 모델명과 펌웨어 버전을 확인할 수 있습니다.

   ![img](/assets/images/sw/rplus1/manager/update_7.png)
4. 다음을 누르면 펌웨어 업데이트를 시작합니다.
   완료될 때 까지 전원이 꺼지거나 케이블이 빠지지 않도록 유의합니다.

   ![img](/assets/images/sw/rplus1/manager/update_8.png)
5. 제어기 펌웨어 설치 결과를 확인합니다.

   ![img](/assets/images/sw/rplus1/manager/update_9.png)

## 펌웨어 복구

   로보플러스 매니저는 제어기의 펌웨어에 문제가 있는 경우 이를 복구 할 수 있습니다.

   CM-150, CM-200 제어기의 경우 최신 로보플러스 매니저(1.0.31.0 이상 버전)에서만 복구가 지원 됩니다.

### 펌웨어 복구 방법

   1. LN-101을  이용해서 제어기와 PC를 연결합니다.
      ![img](/assets/images/parts/controller/cm-200/cm_200_pc.jpg)
   2. 제어기 펌웨어 복구 마법사 실행
      도구 모음의 제어기 복구 버튼을 눌러 제어기 펌웨어 마법사를 실행합니다.
      (CM150, CM-200의 경우 별도의 복구모드 진입과정이 있습니다. 아래 메세지를 참고하세요)
      ![img](/assets/images/sw/rplus1/manager/recovery_1.png)
      ![img](/assets/images/sw/rplus1/manager/cap_2013-12-13_13-12-36-391.png)
   3. 제어기 연결 포트 선택
      펌웨어를 인식하지 못하므로 제어기를 자동 검색할 수 없습니다. 따라서 사용자가 제어기가 연결된 포트를 수동으로 설정해 주어야 합니다. 포트가 사용중이면 제어기를 인식할 수 없으니 다른 프로그램을 종료하고 진행하십시오.
      제어기가 연결된 포트를 선택하고 찾기 버튼을 누르십시오.
      ![img](/assets/images/sw/rplus1/manager/recovery_3.png)
   4. 제어기 전원 껐다 켜기 (CM-150, CM-200은 이과정이 생략됩니다.)
      제어기를 찾기 위해 복구할 제어기의 전원을 껐다가 켜십시오.
      ![img](/assets/images/sw/rplus1/manager/recovery_4.png)
   5. 제어기 정보 확인
      제어기를 찾으면 현재 제어기의 정보와 다운로드 할 펌웨어 정보가 나옵니다. 모델명이 사용자가 연결한 제어기가 맞는지 확인하십시오. (제어기 정보의 버전은 펌웨어 버전이 아니고 부트로더(Boot Loader)의 버전입니다.)
      ![img](/assets/images/sw/rplus1/manager/recovery_5.png)
   6. 펌웨어 복구
      다음 버튼을 클릭하면 펌웨어 복구를 시작합니다. 완료될 때까지 전원이 꺼지거나 케이블이 빠지지 않도록 주의하십시오.
      ![img](/assets/images/sw/rplus1/manager/recovery_7.png)
   7. 제어기 펌웨어 복구 결과를 확인합니다.
      ![img](/assets/images/sw/rplus1/manager/recovery_8.png)

### 관련동영상

제어기 펌웨어 복구하기

<iframe width="640" height="360" src="https://www.youtube.com/embed/ITpIY1lF2As" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>

## 블루투스 통신을 이용한 제어기 펌웨어 복구 방법

### 펌웨어복구

1. 블루투스 동글을 PC USB 포트에 연결 합니다.(CM-150, CM-200)
   (블루투스 기능이 있는 노트북 사용자는 바로 3번 항목으로 진행하세요.)
2. 드라이버가 설치되는 동안 대기합니다.
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_1.png)
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_2.png)
3. 제어기에 BT-110A (또는 BT-210)을 연결하고 전원 버튼을 5초 동안 눌러 "뚜뚜뚜"(3회) 소리가 나면 손을 뗍니다.
4. BT-110A(또는 BT-210)의 파란 불이 켜져있는지 확인 합니다.
5. PC에서 주변의 블루투스 장치를 검색합니다.
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_3.png)
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_4.png)
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_5.png)
6. 검색된 장치들의 ID로 제어기에 연결된 BT-110A(또는 BT-210)이 맞는지 확인 합니다.
   (BT-110A(또는 BT-210)의ID는 모듈 윗면에 적혀 있습니다.)
    ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_6.png)
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_7.png)
7. 장치가 확인 되면 장치에 연결합니다.
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_8.png)
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_9.png)
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_10.png)
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_11.png)
8. COM 포트 번호를 기억합니다.(펌웨어 복구 시 필요합니다.)
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_12.png)
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_13.png)
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_14.png)
9. 로보플러스 프로그램을 실행하고 매니저를 실행합니다.
   ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_15.png)
10. 제어기 펌웨어 복구 마법사 실행
    ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_16.png)
11. 제어기 연결 포트 선택
    STEP8에서 찾은 포트 번호를 선택하고 찾기 버튼을 누르십시오.
    ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_17.png)
12. 제어기 정보 확인
    제어기를 찾으면 현재 제어기의 정보가 나옵니다. 모델명이 사용자가 연결한 제어기가 맞는지 확인하십시오. (제어기 정보의 버전은 펌웨어 버전이 아니고 부트로더(Boot Loader)의 버전입니다.)
    ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_18.png)
13. 복구할 펌웨어 정보확인
    제어기의 정보와 다운로드 할 펌웨어 정보가 나옵니다.
    ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_19.png)
14. 펌웨어 복구
    다음 버튼을 클릭하면 펌웨어 복구를 시작합니다. 완료될 때까지 전원이 꺼지거나 케이블이 빠지지 않도록 주의하십시오.
    ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_20.png)
15. 제어기 펌웨어 복구 결과를 확인합니다.
    ![img](/assets/images/sw/rplus1/manager/fw_bluetooth_21.png)

## 테스트 및 설정

### 제어기
- [CM-5]
- [CM-530]
- [CM-700]

### 다이나믹셀
- [액츄에이터]
- [EX 액츄에이터]
- [MX 액츄에이터]
- [AX-S1]
- [적외선 센서 어레이]

### 기타
- Zig2Serial

[업데이트 및 복구 기능]: ???
[테스트 기능]: ???
[제어기 정보]: ???
[제어기별 관리방법]: ???
[펌웨어복구]: ???
[CM9.04 펌웨어복구]: ???
[CM530, LN101, USB2DXL 해결방법]: http://www.robotis.com/xe/qna_ko/646614
[CM150, CM200 해결방법]: ???
[OpenCM9.04 해결방법]: ???
