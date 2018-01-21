# ROBOTIS OpenCM 개발환경

## 프로그램 실행

프로그램을 실행하면 다음과 같은 화면이 나타납니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_039.png)

Menu :  파일, 편집, 스케치, 도구, 도움말 선택 할 수 있는 영역 입니다.
Toolbar : 자주 쓰는 버튼을 단축 아이콘으로 표시한 영역 입니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_040.gif) 컴파일만 수행하고 실패하거나 성공할 경우 상태바 또는 콘솔에 해당 메시지가 출력됩니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_041.gif) 컴파일을 수행한 후 곧바로 다운로드를 수행합니다. 보드가 반드시 연결된 상태로 실행해야 합니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_042.gif) 새 파일을 시작합니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_043.gif) 파일 불러오기를 수행합니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_044.gif) 현재 상태를 저장합니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_045.gif) 시리얼 모니터를 실행 합니다.

* 에디터(Editor) : 소스를 편집하는 영역 입니다.
* 상태바(Status Bar) : 요청된  기능에 대한 진행 상황을 시각적으로 표시하는 영역 입니다.
* 콘솔(Console) : 현재 커서가 위치한 곳의 라인번호와 선택된 보드와 COM포트를 보여줍니다.
* 탭메뉴(Tab Menu) : 탭을 추가하거나 삭제할 때 선택하는 메뉴 입니다.

## 예제 살펴보기

ROBOTIS OpenCM 개발환경(IDE)은 OpenCM 하드웨어 보드가 제공하는 기능별로 쉬운 예제를 제공하고 있으며, 파일 (예제)Examples 메뉴를 보면 다음과 같이 다양한 예제를 볼 수 있습니다.

![img](/assets/images/sw/opencm_ide/opencm9.04_ide2.png)

## 코드 편집 기능

1. Auto Highliht 기능
   코드 타이핑을 할 때 등록된 키워드는 아래와 같이 검정색에서 노란색 또는 파란색으로 자동으로 하이라이트(highlight)가 됩니다.
   등록된 API라면 아래와 같이 색상이 변하므로 사용하려는 API 이름이 제대로 타이핑 되었는지 확인 할 수 있습니다.

   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide3.png)

   그리고 이러한 자동 하이라이트(Auto highlight) 기능은 아래 경로의 keyword.txt 파일을 이용해서 얼마든지 수정하거나 추가할 수 있습니다,

   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide4.png)
   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide5.png)

2. 자동포맷 기능 사용
   도구 →자동포맷 기능을 활용하면 뒤죽박죽으로 타이핑한 코드들이 보기 좋게 정렬이 됩니다.

   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide6.jpg)

   아래와 같은 코드가 Ctrl+T만 누르면 한번에 보기 좋게 코드가 정렬이 됩니다.

   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide7.jpg)
3. 주석 처리 및 해제
   아래 편집→주석추가/주석삭제를 선택하거나 단축키 Ctrl+/를 누르면 주석처리가 되고 다시 한번 더 누르면 주석이 해제 됩니다.

   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide8.jpg)

   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide9.png)

   위와 같이 블록 처리를 하고 나서 Ctrl+/를 누르면 아래와 같이 주석 처리가 됩니다.
   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide10.png)

   다시 Ctrl+/를 누르면 주석이 해제 됩니다.
4. 들여쓰기 추가 및 삭제
   편집→들여쓰기 추가/삭제를 누르면 현재 커서에서 들여쓰기 단계를 조절 할 수 있습니다. 마찬가지로 Ctrl+}를 누르면 오른쪽으로 한 탭씩 이동하고 Ctrl+}를 누르면 한탭씩 들어갑니다.

   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide11.jpg)

   Ctrl+}를 계속해서 눌러보면 아래와 같이 오른쪽으로 한 탭씩 이동합니다.

   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide12.png)

## 컴파일 및 다운로드 하기

코드를 작성하고 나면 컴파일 메뉴를 이용해 자신이 구현한 코드가 문법에 맞는지 오류가 없는지 체크하면서 프로그래밍을 하는 것이 좋습니다.

![img](/assets/images/sw/opencm_ide/opencm9.04_ide13.png)

>빌드가 성공하게 되면 아래 상태 창에 빌드한 바이너리 사이즈에서 최대 바이너리 사이즈, 그리고 사이즈 대비 점유율이 0%로 나옵니다.

만약에 아래 경로의 Core 경로에 있는 코드들을 수정하였다면 반드시 미리 만들어진 Object 파일들을 지워주어야 한다.

> ROBOTIS\hardware\robotis\cores\robotis

도구 → Clean Objects 메뉴를 클릭하고 새로 빌드를 하면된다. 이 경우 처음은 약간 오래 걸리지만 두번째 부터는 처음에 빌드한 Object 파일들을 재활용하기 때문에 다시 빨라진다.

![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_27.jpg)

Object 파일들은 아래의 Core 경로에 각각의 보드 디렉토리에 저장되어서 재활용된다.

![img](/assets/images/sw/opencm_ide/opencm9.04_ide15.png)

모든 코드가 에러 없이 컴파일이 잘된다면 다운로드를 해보자. 간단히 아래쪽 방향의 화살표를 누르면 컴파일과 다운로드를 한번에 수행하게 된다.

 ![img](/assets/images/sw/opencm_ide/opencm9.04_ide16.jpg)

다운로드가 성공적으로 끝나면 상태바에 Done downloading이라는 메시지와 함께 다운로드한 코드가 OpenCM9.04에서 바로 실행된다.

![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_28.jpg)

## 시리얼 모니터 사용하기

ROBOTIS OpenCM에는 윈도우즈의 하이퍼 터미널이나 TeraTerm과 같은 터미널 프로그램을 Add-on 프로그램으로 기본 제공을 합니다.

![img](/assets/images/sw/opencm_ide/opencm9.04_ide19.jpg)

선택된 COM1번 포트를 통해 통신하고 싶다면 툴바 상단 오른쪽 시리얼 모니터 아이콘을 클릭하면 시리얼 모니터가 실행된다. 참고로 Ctrl + Shift + M 단축키를 눌러서 실행시킬 수 있습니다.

![img](/assets/images/sw/opencm_ide/opencm9.04_ide20.jpg)

![img](/assets/images/sw/opencm_ide/opencm9.04_ide21.jpg)

## 시리얼 모니터 주의사항

OpenCM9.04가 다운로드 중일때는 따로 USB 통신을 할 수 없습니다. 다운로드 중일 때는 시리얼 모니터를 열지 마세요.( 다른 COM포트라면 관계 없습니다.)

### 환경설정(Preference)

파일  → 환경설정(Preference)를 통해 환경설정을 수행합니다.

![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_29.jpg)

![img](http://support.robotis.com/ko/images/product/opencm/904/opencm9.04_30.jpg)

1. 스케치북 위치 : 사용자 기본 작업 디렉토리입니다. 기본적인 스케치 파일의 저장하기 및 불러오기 경로입니다.

   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide24.png)

2. Editor language: 글꼴을 변경합니다.

   ![img](/assets/images/sw/opencm_ide/opencm9.04_ide25.png)

3. 다음 동작중 자세한 출력 보이기 : compilation에 체크를 하면 컴파일 과정중에 자세한 출력을 합니다.
​   Download에 체크를 하면 컴파일 후 다운로드 과정을 자세히 출력합니다.
​   컴파일 및 다운로드가 느려질 수 있으니 꼭 필요하지 않다면 선택하지 않는 것을 추천합니다.
