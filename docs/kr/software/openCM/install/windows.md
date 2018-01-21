
# Windows

## OpenCM9.04와 USB 케이블 준비

USB 케이블은 반드시 안드로이드 폰/패드 Micro-B 타입 USB케이블을 준비합니다.(B타입에는 구성품으로 포함되어 있고 A타입의 경우 악세사리 키트를 통해 구입가능합니다. 안드로이드 스마트폰 케이블 호환됩니다.)

![img](/assets/images/sw/opencm/opencm9.04_windows1.jpg)

<마이크로B USB 케이블 : 안드로이드 스마트폰과 동일>

## ROBOTIS OpenCM 개발환경 Windows 릴리즈 다운로드

 ROBOTIS E-manual(support.robotis.com)사이트에서 최신 버전을 다운로드 받고 압축 파일을 적당한 디렉토리에 풀면 아래와 같이 ROBOTIS_OpenCM.exe 실행파일과 USB 드라이버 폴더(\drivers)가 나타납니다.

![img](/assets/images/sw/opencm/opencm9.04_windows2.png)

<압축을 풀었을 때 나타나는 디렉토리 구조>

참고로 ROBOTIS OpenCM은 별도의 설치 과정이 없이 압축만 풀면 실행할 수 있는 형태의 무설치 프로그램입니다. 제거하고 싶으시면 간단히 디렉토리를 말끔히 지워버리면 됩니다.

## OpenCM9.04를 PC와 연결

USB 드라이버 설치를 위해서 간단히 아래와 같이 PC와 OpenCM9.04를 USB 케이블을 통해 연결합니다.

![img](/assets/images/sw/opencm/opencm9.04_windows3.png)          

<그림 2.4.1-4 OpenCM9.04를 PC와 연결>

단 USB 허브에서 다수의 USB 장치와 함께 연결하는 경우는 되도록 피하고 가급적 PC와 직접 연결하는 방법을 추천합니다. 간혹 허브에서 전류가 충분하지 않으면 다운로드를 실패하는 경우가 발생합니다.

## 드라이버 설치

Window8,10의 경우 "시작설정-> 업데이트 복구-> 복구-> 고급시작옵션-> 문제해결-> 고급옵션-> 시작설정-> 다시시작-> 7)드라이버 서명 하지 않음 선택 후 재부팅" 설정 후 관리자 권한으로 설치 하시기 바랍니다.

이전 단계에서 OpenCM 보드와 PC를 연결하면 아래와 같이 장치관리자에서 “ROBOTIS Virtual COM Port”라는 장치가 나타납니다.

![img](/assets/images/sw/opencm/opencm9.04_windows4.png)

그 장치를 선택하고 “마우스 오른쪽 버튼  드라이버 소프트웨어 업데이트”를 실행 합니다.

![img](/assets/images/sw/opencm/opencm9.04_windows5.png)

다음으로 “컴퓨터에서 드라이버 소프트웨어 찾아보기”를 선택한다.

![img](/assets/images/sw/opencm/opencm9.04_windows6.png)

“찾아보기”를 클릭해서 위에서 압축을 해제한 디렉토리(ROBOTIS\drivers)를 지정한다

![img](/assets/images/sw/opencm/opencm9.04_windows7.png)

다음을 클릭하면 설치가 진행된다.

![img](/assets/images/sw/opencm/opencm9.04_windows8.png)

성공적으로 USB 드라이버를 설치하였다면 아래와 같이 “드라이버 소프트웨어를 업데이트했습니다”라는 창이 나타난다.

![img](/assets/images/sw/opencm/opencm9.04_windows9.png)

여기서 중요한 점은 장치관리자에서 방금 설치하였던 ROBOTIS Virtual COM Port가 COM 포트가 몇 번인지 확인해야 한다.

다른 USB의 포트에 연결하면 COM포트의 번호가 변경될 수 있으니 다른 포트에 연결했다면 다시 확인하고 다운로드를 해야한다.

![img](/assets/images/sw/opencm/opencm9.04_windows10.png)

## ROBOTIS OpenCM.exe 실행

압축을 푼 디렉토리(\ROBOTIS)에 ROBOTIS_OpenCM.exe 파일을 더블클릭 한다.

![img](/assets/images/sw/opencm/opencm9.04_windows11.png)

그러면 아래와 같이 ROBOTIS OpenCM 툴이 실행된다.

![img](/assets/images/sw/opencm/opencm9.04_windows12.png)

## Blink 예제를 Open

파일 → 예제 → 01.Basics → b_Blinlk 순으로 선택한다.

![img](/assets/images/sw/opencm/opencm9.04_windows13.png)

## 보드 선택

 도구 → 보드에서 ROBOTIS OpenCM9.04를 선택합니다.

![img](/assets/images/sw/opencm/opencm9.04_windows14.png)

## 시리얼 포트 선택

반드시  이전 단계에서 확인했던 COM 포트 번호를 선택합니다.

![img](/assets/images/sw/opencm/opencm9.04_windows15.png)

## 다운로드 수행

아래에서 표시된 다운로드 버튼을 클릭합니다. 다운로드가 시작되는 동안 보드의 녹색 LED가 계속 켜집니다. 다운로드가 끝나면 보드가 리셋되고 Blink 예제가 실행되면서 LED가 깜빡입니다.


`notice` 만약에 다운로드 버튼을 클릭하고도 보드의 녹색 Status LED가 켜지지 않는다면 User button을 누른상태에서 USB를 PC와 연결하십시요.
 보드 전원이 들어오면서 녹색 LED가 계속 켜지면 다운로드를 다시 시작하십시요. 자세한 설명은 긴급 복구 모드(강제 다운로드)편을 참조하세요.

![img](/assets/images/sw/opencm/opencm9.04_windows16.png)

![img](/assets/images/sw/opencm/opencm9.04_26.jpg)
