# 포즈 유틸리티

포즈 유틸리티는 미리 입력된 로봇 정보를 이용해서 로봇의 포즈를 보다 쉽게 생성하기 위한 툴입니다.

- 3D 로봇 제어: 3D 로봇의 관절을 마우스로 움직여서 포즈를 만들 수 있습니다.
- 미러: 좌우 대칭 혹은 교환의 방법으로 포즈를 만들 수 있습니다.
- 역기구학: 수학적으로 계산하는 방법으로 포즈를 만들 수 있습니다.

`Note` 포즈 유틸리티는 반드시 로봇 정보가 필요합니다. 즉, 리스트에 없는 로봇은 사용할 수 없습니다. {: .notice}

`Note` 로봇에 따라 3D 로봇이나 미러/역기구학 기능을 지원하지 않을 수 있습니다. {: .notice}

`Note` 포즈 유틸리티는 3D 그래픽 기술을 사용하므로 그래픽 사양이 좋지 않은 시스템에서는 프로그램 속도가 느려질 수 있습니다.{: .notice}

![img](/assets/images/sw/rplus1/motion/poseutility.png)

# 로봇 선택

포즈 유틸리티를 사용하기 위해서는 먼저 포즈 유틸리티를 적용할 로봇을 선택하여야 합니다.

로봇 이름의 리스트를 선택하면 적용할 로봇을 선택할 수 있습니다.

`Note`리스트에 없는 로봇은 포즈 유틸리티를 사용할 수 없습니다.사용자 로봇의 경우는 [기본 포즈 편집기]로만 모션을 만들어야 합니다. {: .notice}

![img](/assets/images/sw/rplus1/motion/poseutility_robotselect.png)

포즈를 만들고자 하는 로봇의 이름을 선택합니다.

| 로봇 이름                   |                         |
| ----------------------- | ----------------------- |
| Bioloid Battle Droid    | 바이올로이드 중급 응용 로봇 배틀 드로이드 |
| Bioloid Dinosaur        | 바이올로이드 고급 응용 로봇 공룡      |
| Bioloid Fawn            | 바이올로이드 중급 응용 로봇 아기 사슴   |
| Bioloid Gerwalk         | 바이올로이드 중급 응용 로봇 거웍      |
| Bioloid Humanoid        | 바이올로이드 고급 응용 로봇 휴머노이드   |
| Bioloid King Spider     | 바이올로이드 고급 응용 로봇 킹 스파이더  |
| Bioloid Puppy           | 바이올로이드 고급 응용 로봇 강아지     |
| Bioloid Spider          | 바이올로이드 중급 응용 로봇 거미      |
| Bioloid Turtle          | 바이올로이드 중급 응용 로봇 거북이     |
| Bioloid Walking Droid   | 바이올로이드 초급 응용 로봇 보행 드로이드 |
| Premium Humanoid A-type | 바이올로이드 프리미엄 휴머노이드 A 타입  |
| Premium Humanoid B-type | 바이올로이드 프리미엄 휴머노이드 B 타입  |
| Premium Humanoid C-type | 바이올로이드 프리미엄 휴머노이드 C 타입  |

초기 자세 버튼을 누르면 로봇이 각 로봇의 타입에 맞는 초기 자세를 취합니다.

# 3D 로봇 제어

## 뷰(View) 제어

3D 화면의 뷰 제어 기능을 이용해서 3D 로봇을 다양한 각도에서 볼 수 있습니다.

![img](/assets/images/sw/rplus1/motion/poseutility_3dview.png)

#### 줌 맞춤(Zoom Fit)

뷰 각도를 초기 상태로 돌려놓습니다.

#### 물체 선택하기

마우스 커서로 관절을 선택할 수 있는 상태로 만듭니다.

#### 뷰(View) 회전시키기

마우스로 뷰를 회전시킬 수 있는 상태로 만듭니다.

마우스 가운데 버튼(휠 버튼)을 누른고 마우스를 움직여도 동일한 효과가 나타납니다.

#### 뷰(View) 이동시키기

마우스로 뷰를 평행 이동시킬 수 있는 상태로 만듭니다.

키보드의 Ctrl키를 누른 상태에서 마우스 가운데 버튼(휠 버튼)을 누르고 마우스를 움직여도 동일한 효과가 나타납니다.

#### 뷰(View) 확대/축소시키기

마우스로 뷰를 확대/축소할 수 있는 상태로 만듭니다.
마우스 휠을 돌려도 동일한 효과가 나타납니다.

## 관절 제어

로봇 위에 나타나는 숫자는 다이나믹셀의 ID를 의미합니다.
ID위에 마우스를 올려 놓으면 선택할 수 있는 다이나믹셀의 색깔이 바뀝니다.

![img](/assets/images/sw/rplus1/motion/poseutility_3djoint1.png)



해당 관절을 마우스로 클릭하면 관절 값이 나타납니다.
관절 값은 모터 값이 아닌 각도로 표시됩니다.

![img](/assets/images/sw/rplus1/motion/poseutility_3djoint2.png)



마우스 왼쪽 버튼을 누른 상태에서 좌/우로 움직이면 값이 증가하거나 감소합니다.

값의 단위는 1024기반 제어인 경우 약0.29(300 / 1024)이고, 4096의 경우 약 0.06(250.92 / 4096)이 됩니다.

# 미러(Mirror)

포즈 유틸리티의 미러 기능은 아래 두 가지 기능을 제공합니다. 기능 선택 후 "적용" 버튼을 누르면 로봇에 적용됩니다.



1. 교환하기
   교환하기는 로봇의 좌측과 우측 포즈를 서로 교환하여 거울을 보듯이 정 반대의 포즈를 만들기 위해 사용합니다.

   ![img](/assets/images/sw/rplus1/motion/poseutility_mirror_exchange.jpg)

   ![img](/assets/images/sw/rplus1/motion/poseutility_mirror1.png)
2. 대칭
   대칭은 좌/우 한 쪽의 포즈를 기준으로 좌/우 대칭이 되도록 반대쪽의 포즈를 만들어 주기 위해 사용합니다.

   ![img](/assets/images/sw/rplus1/motion/poseutility_mirror_symmetry.png)

   ![img](/assets/images/sw/rplus1/motion/poseutility_mirror2.png)

# 역기구학

## 위치(Position)와 좌표계(Coordinate System)

로봇의 움직임에 대한 기구학적 이해의 출발점은 로봇을 구성하는 각 부분의 위치를 파악하는 것에서부터 비롯됩니다. 이를 위해서는 먼저 원점(Origin)이 되는 좌표를 결정하고, 거기에서부터 어느 정도의 위치에 있는지를 변위로 표시해야 합니다.

뷰(View)상에서의 좌표축과 원점은 아래와 같이 나타나며 격자의 단위는 20mm입니다.
Origin은 X, Y, Z의 좌표가 (0, 0, 0)임을 의미합니다.

![img](/assets/images/sw/rplus1/motion/poseutility_vieworigin.png)



## 순기구학(Kinematics)과 역기구학(Inverse Kinematics)

로봇 관절의 각도나 동작으로부터 끝점의 위치나 동작을 구하는 것을 순기구학이라 합니다. 즉, 순기구학은 각 관절의 값이 정해지면 끝점의 위치를 어떻게 구할 것인가 하는 것입니다.

간단한 예로 아래와 같이 평면에서 2개의 관절을 갖는 매니퓰레이터를 생각해 봤을 때, 각 관절의 값이 정해져 있는 경우 그 끝점의 좌표 (x, y)를 구하는 것을 순기구학이라 하며, 순기구학의 해는 오직 하나만 존재합니다.

![img](/assets/images/sw/rplus1/motion/poseutility_ik_kinematics.png)



반대로 끝점의 위치나 동작으로부터 각 관절의 위치나 각도를 구하는 것을 역기구학이라 합니다.

역시 위에서와 같이 평면 2링크 매니퓰레이터를 생각해 봤을 때, 끝점의 좌표 (x, y) 가 정해져 있는 경우 각 관절의 값은 아래 그림과 같이 2 가지 해가 존재합니다.

![img](/assets/images/sw/rplus1/motion/poseutility_ik_inversekinematics.png)

역기구학에서는 경우에 따라 좌표 (x, y) 가 끝점이 다다를 수 없는 거리에 있거나, 관절 각도 제한에 의해 해가 존재하지 않을 수도 있으며, 더 많은 관절을 사용할 경우 무수히 많은 해가 존재할 수도 있습니다.

## 끝점(End Point) 제어

포즈 유틸리티의 역기구학 기능은 초기 자세에서 정해진 끝점을 어느 방향으로 얼마나 옮길 것인가를 선택하면 역기구학을 이용하여 각 관절의 값을 계산하여 자동으로 설정된 값 만큼 끝점을 이동시켜 주는 기능입니다.

이 기능은 역기구학 연산을 수행하는 모듈이 있어야 합니다. 현재 역기구학 연산을 지원하는 로봇은 다음과 같습니다.

- 바이올로이드 휴머노이드
- 바이올로이드 프리미엄 휴머노이드 A타입
- 바이올로이드 프리미엄 휴머노이드 B타입
- 바이올로이드 프리미엄 휴머노이드 C타입

본 주제에 대한 설명은 바이올로이드 프리미엄 휴머노이드 A타입을 기준으로 진행됩니다.



#### 끝점 선택

- Walking Step : 두 발을 모두 움직이는 끝점이며 두 발 가운데에 위치합니다.
- Right Foot : 오른쪽 발만 움직이는 끝점이며 발바닥 가운데에 위치합니다.
- Left Foot : 왼쪽 발만 움직이는 끝점이며 발바닥 가운데에 위치합니다.

 ![img](/assets/images/sw/rplus1/motion/poseutility_ik_selectendpoint.png)

#### 끝점 초기화

끝점의 위치를 초기화시킵니다.

#### 끝점 움직이기

3D 공간에서 끝점은 6개의 파라미터로 제어가 가능합니다. 로봇의 구조에 따라 6개의 파라미터가 모두 나오지 않는 경우도 있습니다.
값을 바꾸기 위해서는 해당 파라미터를 선택한 후, 다음과 같은 방법을 사용합니다.

- 키보드의 [키를 누르면 1씩 감소하고, ]키를 누르면 1씩 증가합니다.
- 키보드의 Shift키를 누른 상태에서 [키를 누르면 10씩 감소하고, ]키를 누르면 10씩 증가합니다.
- 마우스로 더블 클릭을 하거나 키보드 Enter키를 누르면 값을 변경할 수 있는 컨트롤이 나타납니다.

 ![img](/assets/images/sw/rplus1/motion/poseutility_ik_descrip.png)

- X(mm): X축 방향으로 mm단위로 이동합니다.
  ![img](/assets/images/sw/rplus1/motion/poseutility_ik_xmove.png)
- Y(mm): Y축 방향으로 mm단위로 이동합니다.
  ![img](/assets/images/sw/rplus1/motion/poseutility_ik_ymove.png)
- Z(mm): Z축 방향으로 mm단위로 이동합니다.
  ![img](/assets/images/sw/rplus1/motion/poseutility_ik_zmove.png)
- φ(°): X축을 기준으로 각도 단위로 회전합니다.
  ![img](/assets/images/sw/rplus1/motion/poseutility_ik_xamove.png)
- θ(°): Y축을 기준으로 각도 단위로 회전합니다.
  ![img](/assets/images/sw/rplus1/motion/poseutility_ik_yamove.png)
- ψ(°): Z축을 기준으로 각도 단위로 회전합니다.
  ![img](/assets/images/sw/rplus1/motion/poseutility_ik_zamove.png)

`Note`  각 파라미터는 최소 값과 최대 값이 있어서 그 범위에서만 변경이 가능합니다.
  역기구학 연산은 때때로 수학적으로 결과를 알 수 없는 경우가 발생하며, 이를 해(Solution)가 없거나 무수히 많다라고 표현합니다. 이로인해 파라미터 값이 범위 안에 있는데도 불구하고 변경되지 않는 경우가 발생하는데, 이런 경우에는 다른 파라미터 값을 바꾸면 해결이 됩니다.
  (예를 들어, 다리를 끝까지 펴고 있는 경우(Z가 0)에는 X 혹은 Y파라미터가 변경되지 않습니다.) {: .notice}


#### 결과 적용

스텝의 포즈가 선택된 상태에서는 데이터 상의 포즈값이 바뀌고, 로봇의 포즈가 선택된 상태에서는 로봇의 포즈값이 바뀝니다.

# 포즈 실행/캡쳐 (포즈 유틸리티)

![img](/assets/images/sw/rplus1/motion/poseutility_gowritestep.png)

## 스텝의 포즈와 로봇의 포즈

스텝의 포즈는 현재 선택된 모션 파일 상의 스텝을 의미합니다. 즉, 스텝의 포즈가 선택된 상태에서는 포즈 유틸리티에서 바꾼 포즈가 바로 모션 파일에 반영됩니다.

로봇의 포즈는 현재 연결된 로봇을 의미합니다. 즉, 로봇의 포즈가 선택된 상태에서는 포즈 유틸리티에서 바꾼 포즈가 바로 로봇에 반영됩니다.

`Note` 스텝의 포즈는 현재 선택한 페이지에 스텝이 있어야 활성화 됩니다.{: .notice}
`Note` 로봇의 포즈는 로봇이 연결되어야 활성화 됩니다.{: .notice}

## 포즈 실행/캡쳐

기본 포즈 편집기의 [포즈 실행/캡쳐]와 같은 기능입니다.

- 포즈 실행: 스텝의 포즈를 로봇의 포즈에 반영합니다.
- 포즈 캡쳐: 로봇의 포즈를 현재 선택한 스텝의 포즈에 반영합니다.

[기본 포즈 편집기]: ???
[포즈 실행/캡쳐]: ???
