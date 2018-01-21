# Linux

## TOBOTIS OpenCM Linux release 다운로드

사용 중인 Linux가 32bit라면 Linux 32 bit 패키지를 다운로드 받고 64bit이면 Linux 64 bit 패키지를 e-Manual에서 다운로드 받습니다.

다운로드 받고 난 뒤 아래의 커맨드로 압축을 해제합니다. 아래는 32비트 기준으로 설명합니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_027.png)

압축을 풀면 아래와 같이 ROBOTIS 폴더가 생성됩니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_028.png)

## JRE(Java Runtime Environm ent)설치

아두이노와 마찬가지로 ROBOTIS OpenCM 툴도 Java로 만들어진 프로그램이므로 JRE(Java Runtime Environment)가 필요합니다. 윈도우 패키지는 JRE가 패키지에 포함되어 있지만 리눅스 버전은 제외가 되어 있다.

설치가 되어 있으면 다음으로 진행합니다. JRE 설치 확인은 아래와 같이 터미널에서 java –version으로 확인할 수 있습니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_029.png)

위와 같은 응답이 나온다면 JAVA JRE(Java Runtime Environment) 또는 JDK를 설치해야 합니다.
여기서는 openjdk-7-jre-headless를 설치하는 방법을 소개합니다.

```
sudo apt-get install openjdk-7-jre
```

![img](/assets/images/sw/opencm_ide/opencm_ide_030.png)

Java JRE가 성공적으로 설치되었으며 이제 ROBOTIS OpenCM을 실행할 수 있습니다.
## i386 라이브러리 설치하기(Linux 64bit)
Linux 64비트 OS에서 사용하기 위해서는 ia32-libs를 설치해야 합니다.
```
$sudo dpkg –add-architecture i386
$sudo apt-get update
$sudo apt-get install ia32-libs
```

성공적으로 설치가 끝나면 아래와 같이 Processing trigger가 제대로 실행됩니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_031.png)

## ROBOTIS OpenCM 실행

아래와 같이 ROBOTIS_OpenCM를 더블 클릭하거나 터미널에서 ./ROBOTIS_OpenCM을 입력후 엔터를 하면 실행합니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_032.png)

실행 버튼을 클릭합니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_033.png)

그러면 아래와 같이 실행됩니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_034.png)

## Blink 예제 열기

파일 → 예제 → 01. Basics → b_Blink 순으로 선택합니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_035.png)

## 보드선택

도구 → 보드에서 ROBOTIS OpenCM9.04를 선택합니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_036.png)

## 시리얼 포트 선택

시리얼 포트는 ttyACMX로 표시되는데 X는 사용자 PC에 따라 다른 숫자로 표시됩니다.

리눅스/Mac OS X 릴리즈는 커널에 USB CDC드라이버가 포함되어 있으므로 윈도우와 달리 별도의 드라이버를 설치할 필요 없이 바로 사용할 수 있습니다.

![img](/assets/images/sw/opencm_ide/opencm_ide_037.png)

## 다운로드 수행

아래 그림에서 가르키는 다운로드 버튼을 클릭합니다.

다운로드가 시작되는 동안 보드의 녹색 LED가 계속 켜집니다. 다운로드가 끝나면 보드가 리셋되고 Blink 예제가 실행되면서 LED가 깜빡입니다

 `Notice` 만약에 다운로드 버튼을 클릭하고도 보드의 녹색 Status LED가 켜지지 않는다면 User button을 누른상태에서 USB를 PC와 연결하십시요.
 보드 전원이 들어오면서 녹색 LED가 계속 켜지면 다운로드를 다시 시작하십시요. 자세한 설명은 긴급 복구 모드(강제 다운로드)편을 참조하세요. {:. notice}

![img](/assets/images/sw/opencm_ide/opencm_ide_038.png)

![img](/assets/images/sw/opencm/opencm9.04_26.jpg)

그 외에 사용방법은 윈도우즈 버전과 사용법이 동일합니다.
