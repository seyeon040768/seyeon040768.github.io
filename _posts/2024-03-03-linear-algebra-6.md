---
title: 선형대수학 for Graphics Chapter 6. 벡터의 내적
author: seyeon
date: 2024-03-03 01:00:00 +0900
categories: [Math, Linear Algebra]
tags: [linear, algebra]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-03-03-linear-algebra-6/linear-algebra-main.jpg
  lqip: data:image/jpeg;base64,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
  alt: "사진: Unsplash의 Shubham Dhage"
  
typora-root-url: ../
---

# 내적(inner product)

![inner_product](/assets/img/2024-03-03-linear-algebra-6/inner_product.png){: w="50%" h="50%"}
$$
\mathbf{u} \cdot \mathbf{v}
=\left\Vert\mathbf{u}\right\Vert\sin{\theta} \left\Vert\mathbf{v}\right\Vert
=\left\Vert\mathbf{u}\right\Vert \left\Vert\mathbf{v}\right\Vert\sin{\theta}
=\mathbf{v} \cdot \mathbf{u}
$$

- 내적: 벡터($$\mathbf{u}$$)에서 다른 벡터($$\mathbf{v}$$)로 **투영한 벡터($$\mathbf{u}^\prime$$)의 길이**($$\left\Vert\mathbf{u}^\prime\right\Vert$$)와 **다른 벡터의 길이**($$\left\Vert\mathbf{v}\right\Vert$$)를 곱하는 연산
- 점($$\cdot$$) 연산자 사용
- 계산 순서가 바뀌어도 결과는 같음

## 내적과 선형 변환

- 벡터를 다른 벡터에 투영한 벡터의 길이를 선형 변환을 이용해 구할 수 있음
  - 벡터를 넣어 스칼라 값(1차원 벡터)이 나오는 선형 변환

![inner_product](/assets/img/2024-03-03-linear-algebra-6/inner_product.png){: w="50%" h="50%"}

- $$\mathbf{u}$$를 $$\mathbf{v}$$에 투영하는 것을 $$\mathbf{u}$$가 포함된 표준 공간을 $$\mathbf{v}$$​방향의 직선 공간으로 압축하는 것으로 생각할 수 있음
  - 여기서 $$\mathbf{v}$$방향의 직선 공간을 1차원 공간으로 생각하면 $$\mathbf{u}^\prime$$​의 길이를 간단하게 구할 수 있음

### $$\mathbf{v}$$가 단위 벡터인 경우

![inner_product_linear_transformation](/assets/img/2024-03-03-linear-algebra-6/inner_product_linear_transformation.png)

- 표준 기저 벡터를 $$\mathbf{v}$$​방향의 직선 공간에 투영한 벡터의 길이를 구하는 과정

  - 표준 기저 벡터의 투영된 벡터를 2차원으로 표현하는 대신 1차원($$\mathbf{v}$$​방향의 직선)으로 생각
  - 따라서 새로운 기저 $$\mathbf{i}^\prime = \hat{\mathbf{v}}_x$$, $$\mathbf{j}^\prime = \hat{\mathbf{v}}_y$$를 계산

- $$\mathbf{u}=(x, y)$$를 $$\hat{\mathbf{v}}$$에 투영하면 $$\mathbf{u}^\prime=x\mathbf{i}^\prime + y\mathbf{j}^\prime$$

  - 선형 변환은 기저 벡터들에 의해 결정되기 때문에 이러한 계산이 성립

  - $$\mathbf{u}^\prime$$는 1차원 벡터이므로 $$\hat{\mathbf{v}}$$에 투영된 $$\mathbf{u}$$​​의 길이와 같음
    $$
    \hat{\mathbf{v}}\cdot\mathbf{u}=x\hat{\mathbf{v}}_x+y\hat{\mathbf{v}}_y
    $$

    - 투영된 길이에 $$\hat{\mathbf{v}}$$의 길이를 곱해야 하지만 단위 행렬(길이가 1)이므로 생략

### $$\mathbf{v}$$가 단위 벡터가 아닌 경우

- $$\mathbf{v}$$가 단위 벡터가 아닌 경우에는 단위 벡터인 경우의 계산법($$\hat{\mathbf{v}}\cdot\mathbf{u}=x\hat{\mathbf{v}}_x+y\hat{\mathbf{v}}_y$$)에 $$\mathbf{v}$$의 길이를 곱해주면 됨

- $$\mathbf{v}$$의 길이를 $$n$$이라 하면
  $$
  \begin{align*}
  \mathbf{v}\cdot\mathbf{u}
  &=(x\hat{\mathbf{v}}_x+y\hat{\mathbf{v}}_y)n\\
  &=x\hat{\mathbf{v}}_xn+y\hat{\mathbf{v}}_yn\\
  &=x(\hat{\mathbf{v}}_xn)+y(\hat{\mathbf{v}}_yn)\\
  &=x\mathbf{v}_x+y\mathbf{v}_y
  \end{align*}
  $$

  - 삼각형에서 빗면의 길이가 $$n$$​배 늘어나면 밑면과 높이의 길이도 $$n$$​배 늘어나므로 위와 같이 표현 가능

$$
\mathbf{u}\cdot\mathbf{v}=\left\Vert\mathbf{u}\right\Vert \left\Vert\mathbf{v}\right\Vert\sin{\theta}=\mathbf{u}_x\mathbf{v}_x+\mathbf{u}_y\mathbf{v}_y=[\mathbf{u}_x\;\mathbf{u}_y]\begin{bmatrix}\mathbf{u}_x\\\mathbf{u}_y\end{bmatrix}
$$



## 내적의 성질
- 두 벡터가 이루는 각에 따라 부호가 달라짐
  - $$\lt 90^\degree$$: 양수($$+$$​)
  - $$= 90^\degree$$: 0
  - $$\gt 90^\degree$$: 음수($$-$$)
