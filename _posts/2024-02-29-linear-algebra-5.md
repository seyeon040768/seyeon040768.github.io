---
title: 선형대수학 for Graphics Chapter 5. 역행렬, 랭크, 영공간
author: seyeon
date: 2024-02-29 01:00:00 +0900
categories: [Math, Linear Algebra]
tags: [linear, algebra]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-02-29-linear-algebra-5/linear-algebra-main.jpg
  lqip: data:image/jpeg;base64,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
  alt: "사진: Unsplash의 Shubham Dhage"
  
typora-root-url: ../
---

# 역행렬(inverse)

- 선형 변환에서 표준 공간에서의 벡터에 변환 행렬을 곱해 벡터를 변환함
  $$
  \mathbf{v}^\prime=\mathbf{v}\mathbf{T}
  $$
  

- 만약 변환된 벡터를 다시 표준 공간의 벡터로 변환하고 싶다면 변환 행렬의 역행렬을 이용할 수 있음
  $$
  \mathbf{v}^\prime\mathbf{T}^{-1}=\mathbf{v}
  $$

  - 변환 행렬을 역행렬을 변환된 벡터에 곱하면 표준 공간에서의 벡터로 다시 변환시킬 수 있음
  - 예)
    - 시계방향으로 $$90^\degree$$ 회전시키는 변환 행렬의 역행렬: 반시계방향으로 $$90^\degree$$ 회전시키는 변환행렬

- 역행렬을 구할 수 없는 경우

  - 차원을 축소시키는 경우 또는 점(모든 기저 벡터가 영 벡터)으로 변환시키는
  - 예)
    - 2차원 -> 직선
    - 3차원 -> 평면(2차원)
  - 이 경우 행렬식의 값은 0
  - 따라서 정리하면 행렬식이 0이면 역행렬을 구할 수 없음

# 랭크(rank)

## 열, 행공간(column, row-space)

- 행렬의 열, 행들의 선형 결합으로 생성된 벡터들의 집합
- column-major라면 열공간과, row-major라면 행공간과 함께 변환 행렬을 생각할 수 있음

### 행공간과 변환 행렬

- 변환 행렬의 각 행은 기저 벡터에 대한 정보를 담고 있음
  $$
  \begin{bmatrix}
  \leftarrow & \tau(\mathbf{i}) & \rightarrow\\
  \leftarrow & \tau(\mathbf{j}) & \rightarrow\\
  \leftarrow & \tau(\mathbf{k}) & \rightarrow
  \end{bmatrix}
  $$

- 따라서 변환 행렬의 행공간, 즉 변환 행렬의 행들의 선형 결합으로 생성된 벡터는 기저의 벡터 공간과 일치

  - 예)
    $$
    \begin{bmatrix}
    0 & -1\\
    1 & 0
    \end{bmatrix}
    \rightarrow
    x(0, -1)+y(1, 0)
    $$

  

## 랭크

- 행공간 또는 열공간의 차원

  - 행공간과 열공간의 차원은 서로 같음(랭크 값이 같음)

- $$\text{rank}(\mathbf{A})$$: $$\text{rank}()$$ 안에 행렬을 넣어 표시

- 예)
  $$
  \begin{bmatrix}
  0 & -1\\
  1 & 0
  \end{bmatrix}
  $$

  - 시계 방향으로 $$90^\degree$$ 회전시키는 변환 행렬의 행공간은 2차원 전체

  - 따라서 차원은 2

  - $$\text{rank}(\mathbf{T})=2$$로 표기

    ![rank1](/assets/img/2024-02-29-linear-algebra-5/rank1.png){: w="50%" h="50%"}

  $$
  \begin{bmatrix}
  2 & 1\\
  -2 & -1
  \end{bmatrix}
  $$

  - 공간을 $$y=\frac{1}{2}x$$로 축소시키는 변환 행렬의 행공간은 1차원 직선
  - 따라서 차원은 1
  - $$\text{rank}(\mathbf{T})=1$$로 표기

- $$n$$차원 공간에서의 변환 행렬의 랭크 최대값은 $$n$$
  - 만약 $$n$$보다 작다면 공간이 축소된 것이므로 행렬식이 0

# 영공간(null-space) 또는 커널(kernel)

- 선형 변환에 의해 영벡터가 되는 벡터들의 집합

  - $$\mathbf{v}\mathbf{A}=0$$(row-major)

- 예)
  $$
  \begin{bmatrix}
  1 & -1\\
  -1 & 1
  \end{bmatrix}
  $$

  - 위 선형 변환해 의해 원점에서 $$y=x$$ 위의 점을 가리키는 벡터가 모두 $$(0, 0)$$이 됨
  - 여기서 $$y=x$$ 위의 점을 가리키는 모든 벡터, 즉, 영벡터가 되는 모든 벡터들의 집합을 영공간이라고 함

- 공간이 축소되는 경우에만 공집합이 아님

- $$n$$차원에서 $$n-a$$차원으로 축소되는 경우 영공간의 차원은 $$a$$

  - 예)
    - 2차원에서 1차원(직선)으로 축소되는 경우 영공간의 차원은 1차원
    - 3차원에서 1차원(직선)으로 축소되는 경우 영공간의 차원은 2차원(평면)

## nullity

- 영공간의 차원을 $$\text{nullity}(\mathbf{A})$$와 같이 표기

- 예)

  ![nullity1](/assets/img/2024-02-29-linear-algebra-5/nullity1.png){: w="50%" h="50%"}
  $$
  \begin{bmatrix}
  1 & -1\\
  -1 & 1
  \end{bmatrix}
  $$

  - 2차원을 1차원으로 축소시키는 변환 행렬
  - $$\text{nullity}(\mathbf{T})=1$$

# 랭크와 nullity의 관계

- $$\text{rank}(\mathbf{A}_n) + \text{nullity}(\mathbf{A}_n) = n$$
- $$n$$차원 공간을 변형하는 변환 행렬의 랭크와 nullity를 더하면 반드시 $$n$$
  - 랭크는 변환된 공간의 차원, nullity는 축소되어 영벡터가 된 벡터 집합의 차원
  - 따라서 둘이 더하면 반드시 변환 전 공간의 차원일 수 밖에 없음