---
layout: archive
lang: kr
ref: servo_motor
read_time: true
share: true
author_profile: false
permalink: /docs/kr/parts/motor/servo_motor/
sidebar:
  title: Servo Motor
  nav: "servo_motor"
---
# 서보 모터 SM-10

## 부품 사진

![img](/assets/images/parts/motor/servo_motor_product.jpg)

[서보 모터 SM-10]

## 부품 용도

- 올로(OLLO)에서 사용되는 모터로 CM-100 에 연결하여 포트 제어를 통해 동작을 제어할 수 있습니다.
- "회전 모드" 로 설정하면 감속모터와 동일하게 동작시킬 수 있으며, "관절 모드" 로 설정하면 회전 속도(힘)와 위치값 지정을 통해 모터를 지정된 위치까지 움직이도록 할 수 있습니다.
- 관절을 움직이거나 조향장치를 움직이는 등 조건에 따라 특정한 각도를 유지해야 하는 곳에 주로 사용합니다.



## 핀 배열 정보

![img](/assets/images/parts/motor/servo_motor_pinout.png)

1. MOT-
2. GND
3. ADC : 모터의 현재 위치를 아날로그 신호로 출력
4. VCC
5. MOT+



## 제어각

- 올로의 서보 모터는 0도 ~ 300도 까지 위치를 제어할 수 있으며, 최소 제어각은 약 0.29도 (300/1024) 입니다.
- 하지만 올로의 서보모터는 다이나믹셀(Dynamixel)에 비해 정밀하지 못하고, 출력(토크)이 약하기 때문에, 서보모터의 원리와 사용법에 대한 기본적인 학습을 위한 용도로 사용되는 것이 알맞으며, 정밀한 제어를 필요로 하는 곳에 사용하기에는 적합하지 않습니다.

 ![img](/assets/images/parts/motor/servo_motor_01.png)



## H/W 사양

- 무게 : 16g
- 크기 : 18mm * 36mm * 27mm (with horn)
- 기어비 : 194:1
- 속력 : 85 RPM(at 3.0V)
- 특징 :
 - 위치센서(POT)
- 안전장치(클러치) 장착

## 장착 가능한 제어기

- [제어기별 연결장치] 바로가기

## RoboPlus Task 지원 사항

사용 가능한 어드레스 목록 ( [RoboPlus Task] 사용법 참조 )

- 동작모드
- 속도
- 위치


## 관련동영상

 올로 부품 문제해결
 <iframe width="560" height="315" src="https://www.youtube.com/embed/-qRy_NDd5eU" frameborder="0" allowfullscreen></iframe>

 [제어기별 연결장치]: ???
 [RoboPlus Task]: ???
