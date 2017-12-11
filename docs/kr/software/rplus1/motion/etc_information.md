# 기타정보

# 로봇 모션 업로드

제어기에 있는 모션 데이터를 PC로 옮기는 작업을 업로드(Upload)라 합니다.

1. 로봇을 연결하여 로봇 모션 창을 띄웁니다.

   ![img](/assets/images/sw/rplus1/motion/conn_connectmenu.png)
   ![img](/assets/images/sw/rplus1/motion/rmfm_robotmotion.png)

2. 로봇 모션 창을 선택한 후, 다른 이름으로 저장하기 메뉴를 선택합니다.
![img](/assets/images/sw/rplus1/motion/saveas.png)

# 모션 오프셋

오프셋(Offset)이란, 기준 값에 대한 차이를 의미합니다. 모션 오프셋은 기준 모션에 대한 차이를 뜻하고, 기준 모션을 수행하는 로봇을 마스터(Master) 로봇이라 부릅니다.

같은 로봇을 여러 대 만들었을 때, 같은 모션을 실행해도 로봇의 자세는 조금씩 차이가 있습니다. 그 이유는 모터의 위치 편차와 조립 상의 오차때문입니다. 이 차이로 인해 어떤 로봇은 넘어지기도 합니다.

모션 오프셋 개념을 사용하면 모션을 수정하지 않고 로봇마다의 차이를 적용하여 같은 모션을 쓸 수 있습니다.

`Note` 일반적으로 모션 오프셋은 무시할 정도로 작습니다. 하지만, 휴머노이드와 같이 중심을 잡기 어려운 로봇에서는 이 문제가 매우 크게 나타날 수 있습니다. {: .notice}

## 모션 오프셋 편집

로봇의 관절 편차는 모션 오프셋 편집 기능을 이용해서 맞출 수 있습니다.

`Note` 모션 오프셋 메뉴를 선택하면 모든 관절의 토크를 On시켜서 현재 자세를 유지시킵니다. 따라서, 차이를 쉽게 알 수 있는 기준 자세를 미리 취해 놓은 후에 이 기능을 실행하는 것이 좋습니다. {: .notice}

![img](/assets/images/sw/rplus1/motion/offset_menu.png)

해당 관절을 선택한 후, 편집기로 값을 편집할 수 있습니다.

- +값은 모터를 기준으로 CCW방향으로 더 움직인다는 뜻입니다.
- -값은 모터를 기준으로 CW방향으로 더 움직인다는 뜻입니다.

  ![img](/assets/images/sw/rplus1/motion/offset_edit3.png)

## 모션 오프셋 초기화

- 모션 오프셋 값을 모두 0으로 초기화시킵니다.

 ![img](/assets/images/sw/rplus1/motion/offset_reset.png)

## 모션 오프셋 저장

- 현재 수정한 오프셋을 저장시킵니다. 이 기능은 오프셋 정보를 제어기 내부에 저장시킵니다.

  ![img](/assets/images/sw/rplus1/motion/offset_save.png)

## 모션 오프셋 파일로 저장

- 현재 로봇의 오프셋 정보를 파일로 저장하여 PC에 보관할 수 있습니다.
  PC상에 모션 오프셋 파일은 확장자가 ofs인 형태로 존재합니다.

  ![img](/assets/images/sw/rplus1/motion/offset_file_save.png)



## 모션 오프셋 다운로드

- PC에 보관중인 모션 오프셋 파일(ofs)을 로봇에 다운로드할 수 있습니다.

 ![img](/assets/images/sw/rplus1/motion/offset_download.png)

# 전체 페이지 편집

전체 페이지 편집은 모든 페이지에 수정 사항을 반영시킬 때 사용합니다.
전체 페이지 편집이 필요한 경우는 다음과 같습니다.

- 모든 모터의 값을 한꺼번에 바꿉니다.
- ID의 사용 유무를 바꿉니다.

## 해상도 설정

- 모터의 해상도(Resolution)를 설정을 할 수 있습니다.
- 해상도 설정은 실제 로봇이 연결되지 않은 상태에서 모션을 만들때 설정하는 값입니다.
- 다이나믹셀이 연결된 상태에서는 각 다이나믹셀에 맞는 해상도가 자동으로 셋팅되며 변경할 수 없습니다.
- 새롭게 추가된 EX/MX시리즈 모델의 경우에는 4096으로 변환하셔야 하며, 그외의 다이나믹셀은 1024 값으로 사용하시기 바랍니다.
- EX시리즈는 250도까지 위치제어가 가능합니다.
- MX시리즈는 360도까 지 위치제어가 가능합니다.

  ![img](/assets/images/sw/rplus1/motion/dx_resolution.png)

- 해상도를 4096으로 변환 했을때 기본 포즈 편집기에서 기본값을 (512->2048) 로 자동 변환이 됩니다.

  ![img](/assets/images/sw/rplus1/motion/motion_edit.png)

## ID 사용 유무 설정

- RoboPlus Motion은 최대 26개의 모터로 만들어진 로봇의 모션을 지원합니다. (다이나믹셀 ID로 0 ~ 25번까지)
  ID 사용 유무를 설정하여 필요한 ID만 모션 편집시 사용할 수 있습니다.

  ![img](/assets/images/sw/rplus1/motion/page_edit.png)

## ID 교환하기

- ID 교환은 로봇에 사용된 관절의 위치가 바뀐 경우 관절의 위치 값을 손쉽게 바꿀 수 있습니다.
  교환할 2개의 ID를 선택한 후 실행합니다.

  ![img](/assets/images/sw/rplus1/motion/id_change.png)

## 값 모두 바꾸기

- 해당 ID의 관절 값을 특정 값으로 모두 바꾸고 싶을 때 사용합니다.

  ![img](/assets/images/sw/rplus1/motion/value_change.png)

## 값 모두 오프셋 적용

- 오프셋(Offset)이란, 기준에 대해 상대적인 차이를 의미합니다. 해당 ID의 관절 값에 대해 전체적으로 값을 빼거나 더할 때 사용합니다.

  ![img](/assets/images/sw/rplus1/motion/offset_change.png)

# 키보드 단축키 활용 팁

로봇의 모션을 실제로 만들다보면 한손은 로봇을 잡고 있기때문에, 마우스와 키보드를 동시에 사용하는 것이 쉽지 않습니다.
여기서는 키보드만으로 모션을 만들 수 있는 유용한 팁을 알려드립니다.



## 편집창 방향키로 이동하기

- 페이지 편집창, 스텝 편집창, 포즈 편집창을 방향키로 포커스를 이동시킬 수 있습니다.

  ![img](/assets/images/sw/rplus1/motion/arrow_move.png)



## 관절값 키보드로 바꾸기

- [ , ]키를 이용하면 해당 관절 값이 1씩 증가하거나 감소합니다.
- {, }키(Shift + [, ])를 이용하면 해당 관절 값이 10씩 증가하거나 감소합니다.
- Enter키를 누르면 설정창으로 포커스가 이동되고, 수정한 뒤 다시 Enter를 누르면 돌아갑니다.

  ![img](/assets/images/sw/rplus1/motion/joint_move.png)

이 기능이 가능한 편집창은 다음과 같습니다.

- 스텝의 포즈 편집창

  ![img](/assets/images/sw/rplus1/motion/step_move.png)

- 로봇의 포즈 편집창

  ![img](/assets/images/sw/rplus1/motion/robot_move.png)

- 모션 오프셋 편집창

  ![img](/assets/images/sw/rplus1/motion/offset_move.png)

- 로봇의 3D 화면

 ![img](/assets/images/sw/rplus1/motion/poseutility_3djoint2.png)

## 토크 On/Off 키보드로 바꾸기

- 관절을 선택하고 Space키를 누르면 토크 상태가 바뀝니다.

## 스텝별로 로봇 움직이기

- 원하는 스텝을 선택하고 Enter키를 누르면 로봇이 해당 스텝의 포즈를 취합니다. (로봇 모션 창의 경우만 가능)

  ![img](/assets/images/sw/rplus1/motion/step_editor.png)

# 사용자 로봇 만들기

사용자가 만든 로봇을 RoboPlus Motion 프로그램에 추가하여 사용 할 수 있습니다.

`Note` 이 내용은 다음과 같은 전문 지식을 필요로 합니다. {: .notice}
 - XML
 - 3D Graphics
 - C# Programming

## 폴더 구조

RoboPlus Motion이 설치된 폴더 안을 보면 로봇 정보 파일이 아래와 같이 존재합니다.

(예, C:/Program Files/ROBOTIS/RoboPlus/Motion)

-  /Robots: 로봇 정보가 기술된 파일들이 있습니다.
-  /Models: 3D 그래픽을 위한 각 파트들의 모델 데이터가 있습니다.
-  /PlugIn: IK(역기구학)연산 모듈들이 있습니다.

사용자가 자신의 로봇을 만들어 넣기 위해서는 각 폴더에 관련 파일들을 만들어 넣어야 합니다.

## 로봇 정보 파일

로봇 정보 파일에는 RoboPlus Motion이 필요로 하는 모든 정보가 기술되어 있습니다.

이 파일은 rbt라는 확장자로 존재합니다. 포즈 유틸리티의 로봇 리스트는 rbt파일 리스트를 보여주는 것입니다.

![img](/assets/images/sw/rplus1/motion/poseutility_robotselect.png)

로봇 정보 파일은 XML형식으로 관련 정보를 기술합니다. 일반 Text편집기로 파일의 내용을 보면 이를 확인할 수 있습니다.

![img](/assets/images/sw/rplus1/motion/robotinfo_xml.png)

## 1. General

이 부분에는 로봇의 일반적인 정보가 기술되며 필수로 입력해야 합니다.

### 1.1 Name

리스트에 보여질 이름을 입력합니다.

culture속성을 줘서 언어별로 보여지게 할 수 있는데, RoboPlus Motion에서 지원하는 언어만 가능합니다.

| 값    | 언어            |
| ---- | ------------- |
| kor  | 한국어           |
| jpn  | 일본어           |
| 없음   | 영어 혹은 그 외의 언어 |

### 1.2. Motor

로봇에 사용되는 다이나믹셀 정보를 입력합니다.

- id: 다이나믹셀의 ID
- model: 모델명
- init: “초기 자세” 버튼을 눌 러서 취할 포즈의 위치 값

![img](/assets/images/sw/rplus1/motion/poseutility_robotselect.png)

바이올로이드 프리미엄 A타입의 예
```
<Motor id="1" model="AX-12+" init="205"></Motor>
<Motor id="2" model="AX-12+" init="818"></Motor>
<Motor id="3" model="AX-12+" init="251"></Motor>
<Motor id="4" model="AX-12+" init="772"></Motor>
<Motor id="5" model="AX-12+" init="512"></Motor>
<Motor id="6" model="AX-12+" init="512"></Motor>
<Motor id="7" model="AX-12+" init="358"></Motor>
<Motor id="8" model="AX-12+" init="666"></Motor>
<Motor id="9" model="AX-12+" init="512"></Motor>
<Motor id="10" model="AX-12+" init="512"></Motor>
<Motor id="11" model="AX-12+" init="475"></Motor>
<Motor id="12" model="AX-12+" init="549"></Motor>
<Motor id="13" model="AX-12+" init="437"></Motor>
<Motor id="14" model="AX-12+" init="587"></Motor>
<Motor id="15" model="AX-12+" init="549"></Motor>
<Motor id="16" model="AX-12+" init="475"></Motor>
<Motor id="17" model="AX-12+" init="512"></Motor>
<Motor id="18" model="AX-12+" init="512"></Motor>
```

## 2. Mirror

미러(Mirror) 기능을 수행하기 위한 정보입니다. 사용하지 않는다면 입력하지 않아도 됩니다.

![img](/assets/images/sw/rplus1/motion/poseutility_mirror_exchange.jpg)

서로 대칭이 되는 다이나믹셀만 입력합니다. 대칭되는 대상이 없는 경우는 입력하지 않습니다.

- Right: 오른쪽에 해당하는 다이나믹셀 ID
- Left: 왼쪽에 해당하는 다이나믹셀 ID
```
바이올로이드 프리미엄 A타입의 예
<Mirror>
   <Right>1,3,5,9,11,13,15,17</Right>
   <Left>2,4,6,10,12,14,16,18</Left>
</Mirror>
```
![img](/assets/images/sw/rplus1/motion/poseutility_3dview.png)

## 3. InverseKinematics

역기구학 연산을 수행할 모듈을 연결시킵니다. 연산 모듈은 DLL형태로 존재하며 이것은 뒤에서 설명할 [Plug-In SDK 프로그래밍]을 통해 만들 수 있습니다. 사용하지 않는다면 없어도 됩니다.

![img](/assets/images/sw/rplus1/motion/poseutility_ik_selectendpoint.png)
```
바이올로이드 프리미엄 A타입의 예
<InverseKinematics>
   <Module>
      <Name>PremiumHumanoidA.dll</Name>
   </Module>
</InverseKinematics>
```

## 4. Object3D

3D 디스플레이를 위한 로봇 조립 정보가 포함됩니다. 로봇의 조립 정보가 트리(Tree)구조로 형성됩니다.

사용하지 않는다면 없어도 됩니다.

### 4.1. Part

로봇을 구성하는 각 파트 정보가 기술됩니다. 각 파트끼리의 구속관계는 트리(Tree) 구조로 표현됩니다.

-  name: 3D 모델 파일명입니다. 파일 확장자는 제외하고 입력합니다.

(예, f3.igs라면 f3만 입력)

- T: 3D 변환에 사용되는 회전과 이동 정보가 포함된 3x4 행렬입니다.

각 요소는 공백 문자(Space)로 구분됩니다.

![img](/assets/images/sw/rplus1/motion/robotinfo_xml_matrix.png)

- id: 다이나믹셀의 경우 id를 입력합니다.
- type: 움직이는 방법에 대해 정의합니다.

o       모터 몸체가 움직이는 경우는 type을 “body”로 지정합니다.

![img](/assets/images/sw/rplus1/motion/robotinfo_xml_part.png)

```
바이올로이드 프리미엄 A타입의 예
<Object3D>
    <Part name="f51" T="0 0 1 0 1 0 0 0 0 1 0 302.5">
      <Part name ="f3" T="1 0 0 0 0 0 1 -70.5 0 -1 0 19"></Part>
      <Part name ="f3" T="1 0 0 0 0 0 -1 -70.5 0 1 0 -19"></Part>
      <Part name="f52" T="1 0 0 0 0 1 0 0 0 0 1 0">
```

o       몸체는 고정되고 연결된 혼(Horn)이 움직이는 경우는 고정할 대상에 “body”을 지정하고 움직일 대상에 “horn”을 지정합니다.

![img](/assets/images/sw/rplus1/motion/robotinfo_xml_part2.png)

### 3D 모델 데이터

3D 화면에 보여지는 그래픽은 3D 모델 데이터의 역할입니다. 3D 모델 데이터는 여러 3D 모델링 소프트웨어들을 이용해서 만들 수 있습니다. 기본적으로 제공되는 모델 데이터 외에 사용자가 설계한 데이터도 넣을 수 있습니다.

RoboPlus Motion은 IGES(igs)포맷만 지원하며, 데이터 크기가 너무 크면 3D 화면이 느려지게 되므로 되도록이면 데이터 크기를 작게 만드는 것을 권장합니다.

현재 기본으로 제공되는 모델 데이터는 다음과 같습니다. (Models폴더 안에 존재하며  RoboPlus 업데이트 시 추가될 수 있습니다.)

| 이름          | 모양                                       | 파일              |
| ----------- | ---------------------------------------- | --------------- |
| F1          | ![img](/assets/images/sw/rplus1/motion/f1.png) | f1.igs          |
| F2          | ![img](/assets/images/sw/rplus1/motion/f2.png) | f2.igs          |
| F3          | ![img](/assets/images/sw/rplus1/motion/f3.png) | f3.igs          |
| F4          | ![img](/assets/images/sw/rplus1/motion/f4.png) | f4.igs          |
| F5          | ![img](/assets/images/sw/rplus1/motion/f5.png) | f5.igs          |
| F6          | ![img](/assets/images/sw/rplus1/motion/f6.png) | f6.igs          |
| F7          | ![img](/assets/images/sw/rplus1/motion/f7.png) | f7.igs          |
| F8          | ![img](/assets/images/sw/rplus1/motion/f8.png) | f8.igs          |
| F9          | ![img](/assets/images/sw/rplus1/motion/f9.png) | f9.igs          |
| F10         | ![img](/assets/images/sw/rplus1/motion/f10.png) | f10.igs         |
| F11         | ![img](/assets/images/sw/rplus1/motion/f11.png) | f11.igs         |
| F12         | ![img](/assets/images/sw/rplus1/motion/f12.png) | f12.igs         |
| F15 +F16    | ![img](/assets/images/sw/rplus1/motion/f15+16.png) | f15.igs         |
| F51         | ![img](/assets/images/sw/rplus1/motion/f51.png) | f51.igs         |
| F52         | ![img](/assets/images/sw/rplus1/motion/f52.png) | f52.igs         |
| F53         | ![img](/assets/images/sw/rplus1/motion/f53.png) | f53.igs         |
| F56         | ![img](/assets/images/sw/rplus1/motion/f56.png) | f56.igs         |
| F57         | ![img](/assets/images/sw/rplus1/motion/f57.png) | f57.igs         |
| F58         | ![img](/assets/images/sw/rplus1/motion/f58.png) | f58.igs         |
| F60         | ![img](/assets/images/sw/rplus1/motion/f60.png) | f60.igs         |
| WA          | ![img](/assets/images/sw/rplus1/motion/wa.png) | wa,igs          |
| BU          | ![img](/assets/images/sw/rplus1/motion/bu.png) | bu.igs          |
| CM-5        | ![img](/assets/images/sw/rplus1/motion/cm5.png) | cm-5.igs        |
| ADAPTOR-CM5 | ![img](/assets/images/sw/rplus1/motion/adaptor_cm5.png) | adaptor_cm5.igs |
| BATTERY     | ![img](/assets/images/sw/rplus1/motion/battery.png) | battery.igs     |
| AX-12       | ![img](/assets/images/sw/rplus1/motion/ax12.png) | ax-12.igs       |
| AX-12 Horn  | ![img](/assets/images/sw/rplus1/motion/ax12_horn.png) | ax-12_horn.igs  |
| AX-S1       | ![img](/assets/images/sw/rplus1/motion/axs1.png) | ax-s1.igs       |


## Plug-In SDK 프로그래밍

사용자는 Plug-In SDK를 이용해서 포즈 유틸리티의 역기구학 연산 모듈을 추가할 수 있습니다.

설명은 Visual Studio 2005에서 C#으로 개발하는 것을 예로 들었습니다. (Sample 예제 첨부)

`Download`[PlugInSDK_Example.zip](http://support.robotis.com/ko/baggage_files/roboplus/roboplus_motion/pluginsdk_example.zip)  

### 1. 프로젝트 생성

Visual Studio 메뉴에서 “파일->새로 만들기->프로젝트”를 선택한 후, “Visual C#->Windows->클래스 라이브러리” 타입의 프로젝트를 만듭니다.

### 2. 참조 추가

Visual Studio 메뉴에서 “프로젝트->참조 추가”를 선택한 후, 참조 추가 대화 상자에서 “찾아보기” 버튼을 눌러서 RoboPlus가 설치된 폴더에 있는 “Motion->PlugInSDK.dll”을 선택합니다. (예, C:\Program Files\ROBOTIS\RoboPlus\Motion\PlugInSDK.dll”)

### 3. 인터페이스 구현

구현할 Class 파일에 다음과 같이 기술합니다. (예, Class1.cs)
```
using ROBOTIS.MotionEditor.SDK  // namespace 추가
namespace MyPlugIn
{
public class MyPlugIn : IInverseKinematics // 인터페이스 상속
{
}
}
```

커서를 IInverseKinematics 글자에 두고 오른쪽 마우스 버튼을 눌러서 “인터페이스 구현->인터페이스 구현”을 선택하면 구현할 소스가 자동으로 생성됩니다.

### 3.1 CurrentPose

RoboPlus Motion과 주고 받을 Pose 데이터입니다. 사용자는 다음의 규칙을 지켜야 합니다.

- 배열의 생성은 사용자가 직접하며 개수는 26입니다.
- 배열의 인덱스가 다이나믹셀의 ID입니다.
- 해당 ID의 모터에 값을 전달하려면 0~1023 혹은 4096의 값을 넣고, 그렇지 않으려면 -1을 넣습니다.

RoboPlus Motion이 get을 호출할 때는 역기구학(Inverse Kinematics) 연산 결과를 전달해야 하며, set을 호출할 때는 넘겨준 Pose 데이터를 바탕으로 순기구학(Forward Kinematics)을 연산하여 끝점을 알아내야 합니다.

### 3.2 EndPoints

끝점 리스트에 출력될 이름입니다.

![img](/assets/images/sw/rplus1/motion/poseutility_ik_selectendpoint.png)

끝점 리스트 중 선택하거나 선택된 결과를 알아내기 위해서는 아래 인터페이스를 구현합니다.

- SelectedIndex: 끝점의 인덱스
- SelectedEndPoint: 끝점의 이름

### 3.3 X,Y,Z, Roll, Pitch, Yaw

끝점의 3D 로봇의 중심으로부터의 위치 데이터입니다.

사용자 DLL에서 최소값과 최대값을 설정할 수 있습니다.

Roll은 X축 방향의 회전이고, Pitch는 Y축 방향의 회전, Yaw는 Z축 방향의 회전을 의미합니다.

![img](/assets/images/sw/rplus1/motion/poseutility_ik_descrip.png)

- MinX, MinY, MinZ, MinRoll, MinPitch, MinYaw: 끝점 위치의 최소값입니다.
- MaxX, MaxY, MaxZ, MaxRoll, MaxPitch, MaxYaw: 끝점 위치의 최대값입니다.
- 만약, 최소값과 최대값을 같게 만든다면 해당 끝점은 사용하지 않는 것으로 간주되어 리스트에 나타나지 않습니다.
- X, Y, Z, Roll, Pitch, Yaw: 끝점의 위치 값입니다.

### 3.4 Reset

RoboPlus Motion에서 초기화 버튼을 눌렀을 때 호출됩니다.

끝점의 위치 값을 초기화시킵니다.

![img](/assets/images/sw/rplus1/motion/poseutility_ik_selectendpoint.png)

### 4. Plug-In 추가

프로젝트를 빌드를 성공했다면, DLL파일을 RoboPlus Motion폴더내의 “PlugIn” 폴더에 복사합니다. (예, C:\Program Files\ROBOTIS\RoboPlus\Motion\PlugIn)

로봇 정보 파일(rbt)에 역기구학 연산을 할 DLL정보를 기술합니다.

RoboPlus Motion을 실행시켜서 추가시킨 로봇이 잘 동작하는지 확인합니다.

```
바이올로이드 프리미엄 A타입의 예
<InverseKinematics>
   <Module>
      <Name>PremiumHumanoidA.dll</Name>
   </Module>
</InverseKinematics>
```

[Plug-In SDK 프로그래밍]: ???
