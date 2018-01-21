# 라이브러리 사용하기

## 라이브러리 설치하기

라이브러리 설치 방법은 아두이노와 동일합니다. 라이브러리의 경로는 IDE 폴더에서 libraries 입니다.  
```
ROBOTIS\libraries
```

![img](/assets/images/sw/opencm_ide/opencm9.04lib1.png)

Mac의 경우 아래의 경로로 접근하세요

```
 Documents/ROBOTIS/libraries
```
OpenCM의 모든 라이브러리는 다음 RC100 라이브러리 구조와 같은 구조로 등록합니다. 참고로 현재 널리 쓰이고 있는 아두이노 라이브러리들도 아래와 같은 구조로 되어 있으니 OpenCM으로 포팅하기 수월합니다.

(단 Arduino 함수나 헤더파일 이름을 OpenCM에 맞게 수정해야 합니다.)

![img](/assets/images/sw/opencm_ide/opencm9.04lib2.png)

![img](/assets/images/sw/opencm_ide/opencm9.04lib3.png)

위와 같이 libraries폴더 내에 RC100이라는 폴더 이름과 동일한 이름으로 RC100.cpp, RC100.h 파일을 구성합니다. utility 폴더에는 C파일로 짜여진 코드를 넣을 수 있습니다.

examples 폴더에는 해당 라이브러리로 구성된 스케치 예제가 들어갑니다. 예제도 폴더 단위로 구성되며 폴더 이름과 ino파일 이름이 동일하게 해야 인식합니다.

![img](/assets/images/sw/opencm_ide/opencm9.04lib4.jpg)

![img](/assets/images/sw/opencm_ide/opencm9.04lib5.png)
