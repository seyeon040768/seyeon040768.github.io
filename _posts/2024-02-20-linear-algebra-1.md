---
title: 선형대수학 for Graphics Chapter 1. 벡터와 포인트
author: seyeon
date: 2024-02-20 01:00:00 +0900
categories: [Math, Linear Algebra]
tags: [linear, algebra]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-02-20-linear-algebra-1/
  lqip: 
  
typora-root-url: ../
---


# 벡터(vector)
- 방향과 크기(길이)만을 갖는 물리량

  - 굵은 글씨체를 이용해 표기: $$\mathbf{v}$$​

  - 그림으로 나타낼 때는 화살표

  - 원점에서 $$\mathbf{a}$$가 $$x$$축으로는 1, $$y$$축으로는 2만큼 떨어져 있다면 $$\mathbf{a} = (1, 2)$$처럼 나타냄

  - 위치는 포함하지 않음

    ![samevector](/assets/img/2024-02-20-linear-algebra-1/same_vector.png){: w="50%" h="50%"}

    - 따라서 $$\mathbf{v}$$와 $$\mathbf{v}^\prime$$​은 같은 벡터

- 벡터의 방향

  - 원점을 기준으로 어느 곳을 향하는지 나타냄
  - $$\mathbf{a} = (1, 2)$$이면 원점에서 $$(1, 2)$$를 가리킨다는 의미

- 벡터의 크기(길이)

  - 일반적으로 피타고라스의 정리를 이용해 계산
  - $$\mathbf{a} = (1, 2)$$이면 원점에서 $$\left\Vert\mathbf{a}\right\Vert=\sqrt{1^2+2^2}=\sqrt{5}$$

- 단위 벡터(unit vector): 크기가 1인 벡터

  - $$\hat{\mathbf{v}}$$처럼 hat 기호를 이용해 표기
  - 방향만을 나타내기 위해 사용

## 벡터의 합

- 각 원소끼리 덧셈

  - 예) $$(1, 2) + (3, 1) = (4, 3)$$

- 기하적으로는 두 벡터를 연결해 새로운 벡터를 생성하는 것(삼각형법)

  ![triangle](/assets/img/2024-02-20-linear-algebra-1/triangle.png){: w="50%" h="50%"}

  - 다른 방법으로는 평행사변형법이 있음

    ![parallelogram](/assets/img/2024-02-20-linear-algebra-1/parallelogram.png){: w="50%" h="50%"}