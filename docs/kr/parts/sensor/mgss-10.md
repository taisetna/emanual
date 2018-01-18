---
layout: archive
lang: kr
ref: mgss-10
read_time: true
share: true
author_profile: false
permalink: /docs/kr/parts/sensor/mgss-10/
sidebar:
  title: Magnetic Sensor(MGSS-10)
  nav: "mgss-10"
---

# 자석센서 MGSS-10

![](/assets/images/parts/sensors/mgss-10_product.gif)

# [소개](#introduction)

- 자석을 감지하는 센서 입니다.
- 자석을 센서 가까이 대거나 멀리 떨어뜨림에 따라 접촉 센서와 동일하게 동작 합니다.
- 접촉 센서와 다른 점은 자석이 센서의 정면에서 약 5mm까지 떨어져 있더라도 자석이 있음을 감지 할 수 있습니다.

# [사양](#specifications)

- 무게 : 3g
- 크기 : 24mm * 18mm* 12mm

# [센서 감지 범위](#sensing-range)

- 자석의 N/S 극과 센서의 정면까지의 최대 거리 : 1.5Cm
- 주의 : 자석센서의 정면을 제외한 부분은 감지거리가 5mm 보다 짧으면 감지 안될 수 있음

![](/assets/images/parts/sensors/mgss-10_01.png)

# [핀 배열 정보](#pinout)

![](/assets/images/parts/sensors/mgss-10_pinout.gif)

1.  사용안함
2.  GND
3.  ADC : 자석 인식 상태 출력
4.  VCC ( 3.3V / 5V)
5.  사용안함

'Caption' 케이블을 잘못된 방향이나 무리한 힘으로 끼우거나 빼면 커넥터가 파손될 수 있으니 주의해주세요. {: .notice--warning}

'Caption' 제어기의 전원이 반드시 꺼져있는 상태에서 제품을 연결해주세요. 전원이 켜져있는 상태에서 연결 시, 오동작 및 고장을 일으킬 수 있습니다. {: .notice--warning}

# [Tutorials](#tutorials)

- 데이터 읽기는 IR Sensor와 비슷합니다.
- RoboPlus Task : 로보플러스 태스크의 [IR Sensor] 섹션 참조

# [Videos](#videos)

<iframe width="560" height="315" src="https://www.youtube.com/embed/LJ1x6tMrFRE" frameborder="0" allowfullscreen></iframe>

[Controller Compatibility]: /docs/en/parts/controller/controller_compatibility/
[IR Sensor]: /docs/en/software/rplus1/task/programming_02/#ir-sensor
