---
layout: archive
lang: kr
ref: rplus1_task_getting_started
read_time: true
share: true
author_profile: false
permalink: /docs/kr/software/rplus1/task/task/getting_started/
sidebar:
  title: R+ Task 1.0
  nav: "rplustask1"
---

# [개요](#개요)

## [로보플러스 태스크](#로보플러스-태스크)

어떤 일을 처리하기 위한 행동들의 집합을 태스크(Task)라고 합니다. 로봇이 해야할 태스크를 프로그래밍 한 소스를 로보플러스(RoboPlus)에서는 태스크 코드(Task Code)라고 합니다. 로봇은 사용자가 작성한 태스크 코드에 따라 동작하게 되며, 이러한 태스크 코드를 쉽게 작성할 수 있도록 도와주는 것이 로보플러스 태스크(RoboPlus Task) 프로그램입니다.

태스크 코드 파일은 PC 에서 .tsk 라는 확장자를 가지며 좌측과 같은 아이콘으로 표시됩니다.

`참고` 상위버젼의 Task 파일은 하위버젼에서 호환되지 않습니다.
{: .notice}

![R+태스크][R+task]

### [설치하기](#설치하기)

`다운로드` [로보티즈 홈페이지 자료실](#http://www.robotis.com/BlueAD/board.php?bbs_id=service_03)
{: .notice}

로보플러스는 모든 로보티즈 제품을 프로그래밍할 수 있는 통합 소프트웨어입니다.

#### RoboPlus 시스템 요구 사항
+ OS : Windows XP Service Pack 2 이상/ Vista/ 7 (32/64bit)/8 (32/64bit)
+ 800MHz이상의 32비트(x86) 또는 64비트 (x64) 프로세서
+ 3D 가속 기능을 지원하는 그래픽 카드
+ 512MB이상 시스템 메모리
+ 여유공간이 500MB 이상인 하드디스크


`참고` 로보플러스를 실행하기 위해선 .NET FrameWork 3.5이상의 버전이 필요 합니다. 로보플러스 설치시 .NET FrameWork 자동설치가 실패할 경우엔 .NET FreameWork를 별도로 설치하세요.
{: .notice}

#### RoboPlus 설치 실패시

대부분의 RoboPlus 설치 실패의 원인은 사용자 PC환경에 따른 .NET FrameWork 자동 설치 실패 입니다. 따라서 사용자가 직접 .NET FrameWork 3.5를 수동으로 설치 하셔야 합니다.
.NET FrameWork 3.5를 수동으로 설치 하기 전에 Windows installer 3.1이상이 설치 되어 있어야 합니다.

Windows installer와 .NET Framework는 [마이크로소프트 다운로드 센터]에서 다운로드가 가능합니다.

[Windows installer 3.1 다운로드]

[.NET Framework 3.5 다운로드]


# [시작하기](#시작하기)

## [명령줄 만들기](#명령줄-만들기)

명령을 작성하고 싶은 빈 줄을 더블클릭하거나, 마우스를 클릭 후 엔터를 입력하면 선택한 제어기에서 사용할 수 있는 명령을 입력할 수 있습니다.

![명령어 선택][명령어-선택]

만약, 제어기가 선택되어 있지 않다면, 사용자에게 현재 프로그램에서 사용할 제어기를 묻게 됩니다.

![제어기 선택][제어기-선택]

## [파라미터 만들기](#파라미터-만들기)

파라미터(Parameter)는 명령이 수행되기 위해 필요한 대상입니다. 아무것도 설정되지 않았다면 '?'표시로 나타나게 됩니다.

![파라미터][param]

명령을 선택한 다음에는 명령줄을 완성하기 위해 파라미터를 만들어야 합니다.

  1. Enter키를 누르거나 마우스를 더블클릭하여 편집 모드로 들어갑니다.
    ![편집모드][edit]

  2. 좌/우 방향키를 누르거나 마우스로 클릭하면 만들 파라미터를 선택할 수 있습니다.
    ![파라미터 선택][select]

  3. Enter키를 누르거나 마우스를 더블클릭하면 파라미터 선택창이 나타납니다.
    ![파라미터 선택창][select-window]

  4. 적절한 파라미터를 선택합니다. 각 파라미터의 사용법을 익히는 것이 매우 중요합니다.

## [프로그램 다운로드](#프로그램-다운로드)

태스크 코드를 제어기에 다운로드합니다. 다운로드 과정은 제어기 내부에 태스크 코드를 저장하므로 한번만 수행하면 됩니다.

1. PC 와 제어기가 연결되어야 합니다. 태스크 코드를 다운로드하기 위해서는 PC 와 제어기가 연결되어야 합니다. (연결 방법은 각 [제어기 정보]를 참고하세요.)

2. 사용할 통신 포트를 선택해야 합니다. 자동 찾기 기능을 이용하면 쉽게 통신 포트를 설정할 수 있습니다.

    ![통신포트 선택][port-select]

    RoboPlus Task 가 제어기를 찾지 못하면 아래와 같은 에러 메시지가 나타납니다.

    ![에러메세지][error-message]

    PC 와 제어기가 연결되어 있는지 확인합니다. (연결 방법은 각 [제어기 정보]를 참고하세요.)
    제어기의 전원이 켜져 있는지 확인합니다.
    제어기가 연결된 통신 포트가 바르게 선택되어 있는지 확인합니다.

3. 다운로드 메뉴를 선택합니다. 만약, 프로그램에 오류가 있다면 오류를 찾아 수정해야 합니다. ([룰 체크 에러 메시지 확인])

    ![다운로드 선택][download]

4. 다운로드를 진행합니다. 만약 다운로드에 실패했다면 처음부터 다시 시도합니다.

    ![다운로드 진행][download-run]

5. 태스크 코드(Task Code)를 실행합니다. -> 로봇의 동작을 실행 합니다.
    제어기를 켜고 다운로드 한 태스크 코드를 실행합니다. (태스크 코드 실행 방법은 각 [제어기 정보]를  참고하세요.)

### [동영상](#동영상)

1. 로보플러스 프로그램 다운로드(CM-100)

    <iframe width="560" height="315" src="https://www.youtube.com/embed/3mDP9BW-Q0E" frameborder="0" allowfullscreen></iframe>

2. 로보플러스 프로그램 다운로드(CM-510/530)

    <iframe width="560" height="315" src="https://www.youtube.com/embed/dHCqPs1_2yY" frameborder="0" allowfullscreen></iframe>


## [프로그램 결과 출력](#프로그램-결과-출력)

일반적으로 제어기는 PC와 같이 모니터와 같은 출력 장치가 없기 때문에 내부 상태를 확인하기 어렵습니다. 따라서, 터미널(Terminal)이라는 프로그램을 통해 PC 모니터를 빌려쓰는 방식을 사용합니다. RoboPlus Task에는 터미널 프로그램이 포함되어 있어서 제어기의 상태를 확인할 수 있습니다.

![터미널][terminal]


### 프로그램 출력용 모니터 창 띄우기

프로그램 실행 시 화면 출력을 보기 위해서는 반드시 프로그램 실행 전에 `프로그램 출력용 모니터` 창을 띄워야 합니다. 프로그램 출력용 모니터 창을 띄우는 방법은 아래와 같이 여러 가지가 있습니다.

1. 프로그램 다운로드 창에서 프로그램 출력 보기 버튼을 클릭
  ![출력모니터][output-monitor]

2. 도구 모음에서 프로그램 출력 보기 버튼을 클릭
3. 프로그램(P) 메뉴의 프로그램 출력 보기(V) 메뉴 선택 혹은 단축키 F5


### 화면 출력/화면 출력 후 줄바꿈

태스크 코드에 화면 출력 파라미터를 사용하면 원하는 값을 볼 수 있습니다.

![코드][code]

화면 출력 : 값을 출력하고 커서를 옆으로 한 칸 이동시킵니다.

![화면출력][print]

화면 출력 후 줄바꿈 : 값을 출력하고 커서를 다음 줄로 이동시킵니다.

![줄바꿈][newline]

### 화면 출력 내용

1. 제어기 자체 출력 내용
    - 프로그램 시작 메시지가 처음에 출력됩니다.
    
      ![시작메세지][start-message]

    - 프로그램 수행 중 에러 메시지 (에러 메시지 종류 보기)
      ![에러메세지][error-code]

2. 태스크 코드 출력 내용 : -32767 ~ +32767 범위의 10진수로 표시됩니다. (글자는 출력할 수 없습니다.)
    - 숫자를 출력하는 경우
      ![숫자출력][print-num]

    - 센서 값을 출력하는 경우
      ![센서값출력][print-sensor]

### 화면 지우기

화면의 내용을 지울 수 있습니다.

![화면지우기][clear-screen]


## [가상로봇 조종](#가상로봇-조종)

RboPlus Task는 RC-100 등과 같은 조종기가 없어도 조종 기능을 사용할 수 있도록 가상 로봇 조종 기능을 지원하며, 조종기 버튼을 마우스로 클릭하거나 키보드를 이용하여 사용할 수 있습니다.

![가상로봇 조종][virtual-rc100]

키보드 조종은 아래 표를 참고하세요.

|실제 RC-100 키|가상 RC-100의 키보드 키|
| :---: | :---: |
|U|방향키(↑)|
|D|방향키(↓)|
|L|방향키(←)|
|R|방향키(→)|
|1|숫자키(1)|
|2|숫자키(2)|
|3|숫자키(3)|
|4|숫자키(4)|
|5|숫자키(5)|
|6|숫자키(6)|


[마이크로소프트 다운로드 센터]: http://www.microsoft.com/downloads/Search.aspx?displaylang=ko

[Windows installer 3.1 다운로드]: http://www.microsoft.com/downloads/details.aspx?FamilyID=889482fc-5f56-4a38-b838-de776fd4138c&DisplayLang=ko

[.NET Framework 3.5 다운로드]: http://www.microsoft.com/downloads/details.aspx?FamilyID=d0e5dea7-ac26-4ad7-b68c-fe5076bba986&DisplayLang=ko

[R+task]: /assets/images/sw/rplus1/task/roboplus_task_001.png

[명령어-선택]: /assets/images/sw/rplus1/task/roboplus_task_002.png

[제어기-선택]: /assets/images/sw/rplus1/task/roboplus_task_003.png

[param]: /assets/images/sw/rplus1/task/roboplus_task_004.png

[edit]: /assets/images/sw/rplus1/task/roboplus_task_005.png

[select]: /assets/images/sw/rplus1/task/roboplus_task_006.png

[select-window]: /assets/images/sw/rplus1/task/roboplus_task_007.png

[제어기 정보]: #

[룰 체크 에러 메시지 확인]: #

[port-select]: /assets/images/sw/rplus1/task/roboplus_task_008.png

[error-message]: /assets/images/sw/rplus1/task/roboplus_task_009.png

[download]: /assets/images/sw/rplus1/task/roboplus_task_010.png

[download-run]: /assets/images/sw/rplus1/task/roboplus_task_011.png

[terminal]: /assets/images/sw/rplus1/task/roboplus_task_012.png

[output-monitor]: /assets/images/sw/rplus1/task/roboplus_task_013.png

[monitor-btn]: /assets/images/sw/rplus1/task/monitor_btn.png

[code]: /assets/images/sw/rplus1/task/roboplus_task_014.png

[print]: /assets/images/sw/rplus1/task/roboplus_task_015.png

[newline]: /assets/images/sw/rplus1/task/roboplus_task_016.png

[start-message]: /assets/images/sw/rplus1/task/roboplus_task_017.png

[error-code]: /assets/images/sw/rplus1/task/roboplus_task_018.png

[print-num]: /assets/images/sw/rplus1/task/roboplus_task_019.png

[print-sensor]: /assets/images/sw/rplus1/task/roboplus_task_020.png

[clear-screen]: /assets/images/sw/rplus1/task/roboplus_task_021.png

[virtual-rc100]: /assets/images/sw/rplus1/task/virtual_rc100.png
