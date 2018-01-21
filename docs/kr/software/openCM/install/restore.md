# 복구 모드

아래와 같이 Board is not responding 이라는 메시지와 함께 다운로드가 되지 않으면 복구모드를 활용해서 강제로 다운로드 가능합니다.

이렇게 정상 예제를 다운로드를 한번 하고 나면 복구가 되어서 다시 정상적인 다운로드가 됩니다.

![img](/assets/images/sw/opencm_ide/opencm9.04restore1.png)

OpenCM9.04의 User Button을 누른상태에서 USB 케이블로 PC와 직접 연결합니다. 다른 전원 소스는 모두 제거하고 오로지 User Button을 누른 채 USB로만 연결합니다.

![img](/assets/images/sw/opencm/opencm9.04_26.jpg)

> OpenCM9.04는 User Button으로 복구 모드 진입을 할 수 있습니다.

아래 그림과 같이 복구모드로 진입할 경우 녹색 LED가 계속 켜진상태로 있습니다. 정상적으로 다운로드가 끝나면 보드가 리셋되면서 LED는 꺼집니다.

![img](/assets/images/sw/opencm_ide/opencm9.04restore2.jpg)

계속 다운로드 불능상태가 지속되면 작성하신 코드에서 USB 인터럽트를 방해할 만한 코드들을 제거하셔야 합니다.
