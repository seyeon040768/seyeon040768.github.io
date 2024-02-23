---
title: 선형대수학 for Graphics Chapter 2. 기저와 선형 결합
author: seyeon
date: 2024-02-22 01:00:00 +0900
categories: [Math, Linear Algebra]
tags: [linear, algebra]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-02-22-linear-algebra-2/linear-algebra-main.jpg
  lqip: data:image/jpeg;base64,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
  alt: "사진: Unsplash의 Shubham Dhage"
  
typora-root-url: ../
---

# 기저(basis)

- $$\mathbf{v} = (2, 3)$$은 $$\mathbf{v}$$가 $$x$$축으로 $$+2$$만큼, $$y$$축으로 $$+3$$만큼 이동한 곳을 가리킨다고 할 수 있음
- 이것을 수식으로 나타내면 $$\mathbf{v}=2(1, 0) + 3(0, 1)$$처럼 표현 가능
  - 여기서 $$(1, 0)$$, $$(0, 1)$$​처럼 특정 벡터 공간의 근본이 되는 벡터를 **기저**라고 함
    - $$(1, 0)$$은 $$x$$축을 나타내고 $$(0, 1)$$은 $$y$$축을 나타냄
  - $$(1,0)$$, $$(0, 1)$$뿐만 아니라 모든 벡터가 기저가 될 수 있음
- 표준 기저 벡터(standard basis vector)
  - $$\hat{\mathbf{i}}$$: 일반적으로 $$x$$축을 의미, $$(1, 0)$$
  - $$\hat{\mathbf{j}}$$: 일반적으로 $$y$$축을 의미, $$(0, 1)$$
  - 모든 벡터는 표준 기저 벡터 * 스칼라의 합으로 표현 가능
    - 예) $$(2, 3) = 2\hat{\mathbf{i}} + 3\hat{\mathbf{j}}$$

# 선형 결합(linear combination)

- 벡터를 스칼라 * 벡터들의 합으로 나타내는 것
  - 예) $$(2, 3) = 2\hat{\mathbf{i}} + 3\hat{\mathbf{j}}$$

## 선형 결합과 기저 벡터

- 특정 벡터 공간에서 정의된 벡터를 표준 벡터 공간에서 알고 싶다면 해당 공간의 기저 벡터와 선형 결합을 하면 됨
- 예)

  ![basis_uv](/assets/img/2024-02-22-linear-algebra-2/basis_uv.png){: w="50%" h="50%"}*$$\mathbf{u}$$와 $$\mathbf{v}$$가 이루는 벡터 공간*

  - $$x$$축을 나타내는 기저: $$\mathbf{u}=(2, 1)$$
  - $$y$$축을 나타내는 기저: $$\mathbf{v} = (1, 1)$$​
  - 벡터 $$\mathbf{u}$$와 $$\mathbf{v}$$가 이루는 벡터 공간에서 정의된 벡터 $$\mathbf{a}=(1, 2)$$​
    - $$\mathbf{u}$$ 방향으로 $$+1$$만큼, $$\mathbf{v}$$ 방향으로 $$+2$$​만큼 떨어진 곳을 가리키는 벡터

  ![uv_to_standard](/assets/img/2024-02-22-linear-algebra-2/uv_to_standard.png){: w="50%" h="50%"}*표준 벡터 공간에서 표현한 $$\mathbf{a}$$*

  - $$\mathbf{a}$$를 표준 기저 벡터가 이루는 공간에서 표현하고 싶다면 $$a_x\mathbf{u} + a_y\mathbf{v} = 1(2, 1) + 2(1, 1) = (4, 3)$$
  - 즉, $$\mathbf{a}$$를 표준 벡터 공간에서는 $$(4, 3)$$​로 나타낼 수 있음

![changing_coordinate_vector](/assets/img/2024-02-22-linear-algebra-2/changing_coordinate_vector.png)*일반화한 그림*
$$
\mathbf{p}_B = (x', y') = x\mathbf{u} + y\mathbf{v}
$$
