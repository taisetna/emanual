# 포즈 편집

포즈(Pose)란, 로봇의 정지된 자세를 뜻하며 해당 자세를 취하기 위해 필요한 모터들의 위치 값의 집합으로 표현됩니다.

![img](/assets/images/sw/rplus1/motion/poseedit_concept.png)

### 스텝의 포즈

데이터로 저장된 상태의 포즈를 스텝의 포즈라고 부릅니다.

### 로봇의 포즈

연결된 로봇의 관절별 위치 값들을 로봇의 포즈라고 부릅니다.

로봇의 포즈는 수정하면 로봇이 움직입니다.

## 기본 포즈 편집기

기본 포즈 편집기는 어떤 형태의 로봇도 사용할 수 있는 기본적인 편집기입니다.
만약, 스텝의 포즈에서 사용하는 ID 개수를 변경하거나  바꾸고 싶다면 [ID편집 기능]을 사용할 수 있습니다.

![img](/assets/images/sw/rplus1/motion/basic_motion_edit.png)

## 관절 선택하기

마우스로 해당 줄을 클릭하면 1개의 관절을 선택할 수 있습니다.
여러 개의 관절을 선택하는 방법은 다음과 같습니다.

- 연속적으로 여러 관절을 선택

 ![img](/assets/images/sw/rplus1/motion/basic_joint_selection_3.png)

 - 마우스로 드래그(Drag)합니다.

 - Shift키를 누른 상태에서 다른 관절을 선택합니다.

- 개별적으로 여러 관절을 선택

 ![img](/assets/images/sw/rplus1/motion/basic_joint_selection_4.png)

 - Ctrl키를 누른 상태에서 해당 관절을 선택합니다.

- 전체 관절 선택

 - 버튼을 눌러서 선택

   ![img](/assets/images/sw/rplus1/motion/basic_joint_selection_1.png)

 - 메뉴를 선택

   ![img](/assets/images/sw/rplus1/motion/basic_joint_selection_2.png)

## 토크 On/Off

토크 On/Off 기능은 로봇 관절의 힘을 켜거나 끄거나해서 손으로 포즈를 잡을 수 있도록 합니다.
토크 On/Off기능은 로봇의 포즈에서만 사용할 수 있습니다.
토크 On인 상태에서는 위치 값이 출력되고, Off인 상태에서는 '꺼짐'표시로 출력됩니다.

![img](/assets/images/sw/rplus1/motion/basic_torque_1.png)

토크를 On/Off시키는 방법은 다음과 같습니다.

- "켜기"버튼을 누르면 선택된 관절의 토크가 On됩니다.

 ![img](/assets/images/sw/rplus1/motion/basic_torque_2.png)

- "끄기"버튼을 누르면 선택된 관절의 토크가 Off됩니다.

 ![img](/assets/images/sw/rplus1/motion/basic_torque_3.png)

- 토크 토글(Toggle) 기능은 선택된 관절의 토크 On/Off상태를 전환시킵니다.

 ![img](/assets/images/sw/rplus1/motion/basic_torque_4.png)

## 관절 값 바꾸기

포즈에서 관절을 선택하면 해당 모터의 위치 값을 바꿀 수 있습니다.

 ![img](/assets/images/sw/rplus1/motion/basic_joint_value_1.png)



## 포즈 실행/캡쳐

### 포즈 실행

포즈 실행은 스텝의 포즈를 로봇의 포즈로 옮겨서 로봇이 해당 포즈를 취하게 합니다.

![img](/assets/images/sw/rplus1/motion/stepwritebutton.png)

![img](/assets/images/sw/rplus1/motion/basic_pose_1.png)



### 포즈 캡쳐

포즈 캡쳐(Capture)란, 로봇의 포즈를 스텝의 포즈로 옮겨서 데이터에 저장합니다.

![img](/assets/images/sw/rplus1/motion/stepgobutton.png)

![img](/assets/images/sw/rplus1/motion/basic_pose_2.png)

## 포즈 복사/붙여넣기

포즈 복사/붙여넣기 기능은 매우 쉽게 관절 값을 교환할 수 있도록 합니다.
포즈끼리의 교환은 물론 엑셀(Excel)이나 다른 문서에서 사용되는 텍스트도 교환이 가능합니다.
(일반 텍스트의 경우 숫자 구분자는 공백 문자(Space)와 엔터(Enter), 탭(Tab)만 가능합니다.)

![img](/assets/images/sw/rplus1/motion/pose_copy_from_pose.png)
![img](/assets/images/sw/rplus1/motion/pose_copy_from_memo.png)



- 포즈 복사: 메뉴를 선택하거나 Ctrl+C를 눌러서 실행합니다.

 ![img](/assets/images/sw/rplus1/motion/pose_copy.png)

- 포즈 붙여넣기: 메뉴를 선택하거나 Ctrl+V를 눌러서 실행합니다.

 ![img](/assets/images/sw/rplus1/motion/pose_paste.png)

## 포즈 마스크

포즈 마스크(Mask)는 포즈 실행/캡쳐시 값의 사용 유무를 설정함으로써 2개의 포즈를 합쳐서 새로운 포즈를 만들어냅니다.
예를 들어 A라는 포즈의 상체 포즈와 B라는 포즈의 하체 포즈를 합쳐서 C라는 포즈를 만드는 등의 작업을 할 수 있습니다.

![img](/assets/images/sw/rplus1/motion/pose_mask.png)

![img](/assets/images/sw/rplus1/motion/pose_mask_pic.png)

[ID편집 기능]: ??
