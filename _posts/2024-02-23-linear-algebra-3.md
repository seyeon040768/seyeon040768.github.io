---
title: 선형대수학 for Graphics Chapter 3. 행렬과 선형 변환
author: seyeon
date: 2024-02-23 01:00:00 +0900
categories: [Math, Linear Algebra]
tags: [linear, algebra]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-02-23-linear-algebra-3/linear-algebra-main.jpg
  lqip: data:image/jpeg;base64,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
  alt: "사진: Unsplash의 Shubham Dhage"
  
typora-root-url: ../
---

# 행렬(matrix)

- 행렬: 수를 행(row)과 열(column)에 맞춰 배열한 것
  $$
  \begin{bmatrix}
  1 & 2 & 3\\
  4 & 5 & 6\\
  7 & 8 & 9
  \end{bmatrix}
  $$

  - 3*3 형태의 행렬

- $$\mathbf{T}$$: 대문자 굵은 글씨체로 표현

- 대괄호($$[]$$)나 소괄호($$()$$)로 감싸 표현

- 행렬은 벡터를 나열한 것으로 생각할 수 있음

  $$
  \begin{bmatrix}
  1 & 2 & 3\\
  4 & 5 & 6\\
  7 & 8 & 9
  \end{bmatrix}
  ,\quad
  \begin{bmatrix}
  1\\
  4\\
  7
  \end{bmatrix}
  \begin{bmatrix}
  2\\
  5\\
  8
  \end{bmatrix}
  \begin{bmatrix}
  3\\
  6\\
  9
  \end{bmatrix}
  ,\quad
  \begin{matrix}
  [1 & 2 & 3]\\
  [4 & 5 & 6]\\
  [7 & 8 & 9]
  \end{matrix}
  $$

- row-major vs column-major
  - row-major: 행을 중점으로 표기
    - 위에 식에서 3번째 경우
    - directx에서 사용하는 방식
  - column-major: 열을 중점으로 표기
    - 위에 식에서 2번째 경우
    - opengl에서 사용하는 방식

## 행렬의 덧셈

- 같은 위치에 있는 원소를 덧셈
  $$
  \begin{bmatrix}
  1 & 2\\
  3 & 4
  \end{bmatrix}
  +
  \begin{bmatrix}
  5 & 6\\
  7 & 8
  \end{bmatrix}
  =
  \begin{bmatrix}
  6 & 8\\
  10 & 12
  \end{bmatrix}
  $$

- 따라서 모양이 다른 두 행렬은 서로 더할 수 없음

## 행렬의 곱셈

### 스칼라 곱

- 각 원소에 스칼라 값을 곱셈

    $$
    2\begin{bmatrix}
    1 & 2\\
    3 & 4
    \end{bmatrix}
    =
    \begin{bmatrix}
    2 & 4\\
    6 & 8
    \end{bmatrix}
    $$

### 행렬 곱

- 앞 행렬의 행과 뒤 행렬의 열을 곱셈
  $$
  \begin{bmatrix}
  a & b & c\\
  d & e & f
  \end{bmatrix}
  \begin{bmatrix}
  a' & b'\\
  c' & d'\\
  e' & f'
  \end{bmatrix}
  =
  \begin{bmatrix}
  aa'+bc'+ce' & ab'+bd'+cf'\\
  da'+ec'+fe' & db'+ed'+ff'
  \end{bmatrix}
  $$

- 따라서 앞 행렬의 열의 개수와 뒤 행렬의 행의 개수가 같아야 함
  - $$a\times b$$ 크기의 행렬과 $$b\times c$$ 크기의 행렬을 곱한 행렬의 크기는 $$a\times c$$​
- 행렬 곱은 순서가 바뀌면 결과가 달라지거나 모양이 달라 곱할 수 없음

## 전치 행렬(transpose)

- 행렬의 행과 열을 교환한 행렬

  - 위첨자 $$T$$를 이용해 표기
    - 예) $$\mathbf{A}^T$$
  - $$y=-x$$ 그래프(주 대각선)를 기준으로 뒤집은 형태

  $$
  \begin{bmatrix}
  1 & 2 & 3\\
  4 & 5 & 6
  \end{bmatrix}^T
  =
  \begin{bmatrix}
  1 & 4\\
  2 & 5\\
  3 & 6
  \end{bmatrix}
  $$

  

## 항등 행렬(identity)

$$
\begin{bmatrix}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix}
$$

- 주 대각 성분이 1이고 나머지는 0인 정사각행렬

- $$\mathbf{I}$$로 표기
- $$\mathbf{I} \times \mathbf{A}$$는 언제나 $$\mathbf{A}$$​

## 역행렬(inverse)

- 행렬과 곱했을 때 항등 행렬이 되는 행렬
  - $$\mathbf{A}\mathbf{A}^{-1}=\mathbf{I}$$
- 위첨자 $$-1$$를 이용해 표기
  - 예) $$\mathbf{A}^{-1}$$

# 선형 변환(linear transformation)

- 선형 변환: 벡터 공간을 다른 벡터 공간으로 변환하며 다음 조건을 만족하는 함수

$$
\begin{align*}&\tau(\mathbf{u}+\mathbf{v})=\tau(\mathbf{u})+\tau(\mathbf{v})\\&\tau(k\mathbf{u})=k\tau(\mathbf{u})\end{align*}
$$

- 위 조건을 만족하면 $\tau$는 선형 변환
- 선형 변환이 아닌 경우

    $$
    \tau(x, y, z)=(x^2, y^2, z^2)
    $$

    - 위의 경우 두 조건 모두 만족하지 않음
    - 따라서 선형 변환이 아님

## 선형 변환과 벡터 공간

- 선형 변환의 조건

  - 선형 변환 전 벡터 공간과 후 벡터 공간의 원점은 일치해야 함
  - 선형성(직선)이 유지되어야 함

- $$\mathbf{i}$$를 $$(1, 2)$$로, $$\mathbf{j}$$를 $$(3, 0)$$으로 변환하는 선형 변환의 경우
  $$
  (x', y') = x(1, 2) + y(3, 0) = (x + 3y, 2x)
  $$

  - 위와 같이 변형된 벡터 공간에 속하는 벡터가 어떻게 변하는지 알 수 있음

## 변환 행렬

$$
(x', y') = x(1, 2) + y(3, 0) = (x + 3y, 2x)
$$

- 위 식을 행렬로 간단하게 표현할 수 있음
  $$
  [x, y]
  \begin{bmatrix}
  1 & 2\\
  3 & 0
  \end{bmatrix}
  =
  [x + 3y, 2x]
  $$

- 정리하면 $$\mathbf{i}$$를 $$(1, 2)$$로, $$\mathbf{j}$$를 $$(3, 0)$$으로 변환하는 선형 변환 $$\tau$$를 행렬(row-major)로 표현하면
  $$
  \begin{bmatrix}
  \leftarrow & \tau(\mathbf{i}) & \rightarrow\\
  \leftarrow & \tau(\mathbf{j}) & \rightarrow
  \end{bmatrix}
  $$

  - 위와 같이 행으로 쌓는 형태

- 이처럼 선형 변환을 계산하는 행렬을 **변환 행렬**이라함

- 만약 row-major 변환 행렬을 column-major로 바꾸고 싶다면 전치 행렬을 구하면 됨

## 변환(회전, 이동, 스케일링)

### 회전(2d)

![cos_sin_rotate](/assets/img/2024-02-23-linear-algebra-3/cos_sin_rotate.png){: w="50%" h="50%"}
$$
\begin{align*}&x^\prime=x\cos{\theta}-y\sin{\theta}\\ & y^\prime=x\sin{\theta}+y\cos{\theta}\end{align*}
$$

- 회전은 선형 변환
  $$
  \begin{align*}
  \text{Function:}\quad&\tau(x, y) = (x \cos\theta - y \sin\theta, x \sin\theta + y \cos\theta) \\
  \text{Additivity:} \quad &\tau(u_1 + v_1, u_2 + v_2) \\
  &= ((u_1 + v_1) \cos\theta - (u_2 + v_2) \sin\theta, (u_1 + v_1) \sin\theta + (u_2 + v_2) \cos\theta) \\
  &= (u_1 \cos\theta - u_2 \sin\theta + v_1 \cos\theta - v_2 \sin\theta, u_1 \sin\theta + u_2 \cos\theta + v_1 \sin\theta + v_2 \cos\theta) \\
  &= \tau(u_1, u_2) + \tau(v_1, v_2) \\
  \text{Homogeneity:} \quad &\tau(ku_1, ku_2) \\
  &= (ku_1 \cos\theta - ku_2 \sin\theta, ku_1 \sin\theta + ku_2 \cos\theta) \\
  &= k(u_1 \cos\theta - u_2 \sin\theta, u_1 \sin\theta + u_2 \cos\theta) \\
  &= k \tau(u_1, u_2)
  \end{align*}
  $$
  
- 따라서 변환 행렬(row-major)을 만들 수 있음

$$
\left[x^\prime , y^\prime \right] = \left[ x, y \right]\left[\begin{matrix}\cos{\theta} & \sin{\theta}\\ -\sin{\theta} & \cos{\theta}\end{matrix}\right]
$$

### 회전(3d)

![rotate](/assets/img/2024-02-23-linear-algebra-3/rotate.png){: w="70%" h="70%"}

- $$\mathbf{n}$$: 회전축, 단위 벡터

- $$\mathbf{v}$$: 회전시킬 벡터

- $$R_\mathbf{n}$$: $$\mathbf{n}$$을 기준으로 회전시키는 함수
  - 이를 수행하는 행렬을 찾는 것이 목표
  
- 회전 과정
  1. \$\text{proj}_\mathbf{n}(\mathbf{v})=(\mathbf{n}\cdot\mathbf{v})\mathbf{n}$
  2. $$\mathbf{v}*\bot=\mathbf{v}-\text{proj}*\mathbf{n}(\mathbf{v})$$: $$\mathbf{v}$$에 수직(perpendicular)한 벡터
  3. $$\mathbf{n}\times\mathbf{v}$$: $$\mathbf{v}_\bot$$과 수직이며 길이가 같음
       - \$\left\Vert\mathbf{n}\times\mathbf{v}\right\Vert=\left\Vert\mathbf{n}\right\Vert\left\Vert\mathbf{v}\right\Vert\sin{\alpha}=\left\Vert\mathbf{v}_\bot\right\Vert$
  4. \$R_\mathbf{n}(\mathbf{v}\ast\bot)=\cos\theta\mathbf{v}\ast\bot+\sin\theta(\mathbf{n}\times\mathbf{v})$
  5. \$R_\mathbf{n}(\mathbf{v})=\text{proj}\ast\mathbf{n}(\mathbf{v})+R\ast\mathbf{n}(\mathbf{v}_\bot)$

- 변환 행렬
  - Rodrigues’ rotation formula(로드리게스 회전 공식)

  $$
  \begin{align*}R_\mathbf{n}(\mathbf{v})&=\text{proj}*\mathbf{n}(\mathbf{v})+R*\mathbf{n}(\mathbf{v}*\bot)\\&=(\mathbf{n}\cdot\mathbf{v})\mathbf{n}+\cos\theta\mathbf{v}*\bot+\sin\theta(\mathbf{n}\times\mathbf{v})\\&=(\mathbf{n}\cdot\mathbf{v})\mathbf{n}+\cos\theta(\mathbf{v}-(\mathbf{n}\cdot\mathbf{v})\mathbf{n})+\sin\theta(\mathbf{n}\times\mathbf{v})\\&=\cos\theta\mathbf{v}+(1-\cos\theta)(\mathbf{n}\cdot\mathbf{v})\mathbf{n}+\sin\theta(\mathbf{n}\times\mathbf{v})\end{align*}
  $$

  - 표준 기저 벡터 대입($$c=\cos\theta$$, $$s=\sin\theta$$)

  $$
  R_\mathbf{n} = \begin{bmatrix} \leftarrow&R_\mathbf{n}(\mathbf{i})&\rightarrow\\ \leftarrow&R_\mathbf{n}(\mathbf{j})&\rightarrow\\ \leftarrow&R_\mathbf{n}(\mathbf{k})&\rightarrow \end{bmatrix} = \begin{bmatrix} c + (1-c)x^2 & (1-c)xy + sz & (1-c)xz - sy\\ (1-c)xy - sz & c + (1-c)y^2 & (1-c)yz + sx\\ (1-c)xz + sy & (1-c)yz - sx & c + (1-c)z^2 \end{bmatrix}
  $$

  - $$\mathbf{n}$$이 $$x$$축인 경우($$x=1, y=0, z=0$$)

  $$
  R_\mathbf{x} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & \cos\theta & \sin\theta \\ 0 & -\sin\theta & \cos\theta \end{bmatrix}
  $$

  - $$\mathbf{n}$$이 $$y$$축인 경우($$x=0, y=1, z=0$$)

  $$
   R_\mathbf{y} = \begin{bmatrix}\cos\theta & 0 & -\sin\theta \\0 & 1 & 0 \\\sin\theta & 0 & \cos\theta\end{bmatrix}
  $$

  - $$\mathbf{n}$$이 $$z$$축인 경우($$x=0, y=0, z=1$$)

  $$
  R_\mathbf{z} = \begin{bmatrix} \cos\theta & \sin\theta & 0 \\ -\sin\theta & \cos\theta & 0 \\ 0 & 0 & 1 \end{bmatrix}
  $$

  - 역행렬
    $$
    R_\mathbf{n}^{-1}=R_\mathbf{n}^T = \begin{bmatrix}c + (1-c)x^2 & (1-c)xy - sz & (1-c)xz + sy\\(1-c)xy + sz & c + (1-c)y^2 & (1-c)yz - sx\\(1-c)xz - sy & (1-c)yz + sx & c + (1-c)z^2\end{bmatrix}
    $$
    
  
  
    - 회전 변환 행렬의 역변환 행렬은 전치 행렬과 같음

### 스케일링(scaling)

$$
S(x, y, z) = (s_xx, s_yy, s_zz)
$$

- $$x$$방향으로는 $$s_x$$만큼, $$y$$방향으로는 $$s_y$$만큼, $$z$$방향으로는 $$s_z$$만큼 변형

- 스케일링도 선형 변환이므로 변환 행렬을 구할 수 있음
  $$
  \begin{align*}&S(\mathbf{i})=(s_x\cdot1, s_y\cdot0, s_z\cdot0)=(s_x, 0, 0)\\&S(\mathbf{j})=(s_x\cdot0, s_y\cdot1, s_z\cdot0)=(0, s_y, 0)\\&S(\mathbf{k})=(s_x\cdot0, s_y\cdot0, s_z\cdot1)=(0, 0, s_z)\end{align*}
  $$

  $$
  \mathbf{S}=\begin{bmatrix}s_x&0&0\\0&s_y&0\\0&0&s_z\end{bmatrix}\quad\mathbf{S}^{-1}=\begin{bmatrix}1/s_x&0&0\\0&1/s_y&0\\0&0&1/s_z\end{bmatrix}
  $$

  

- 예)

  ![scaling](/assets/img/2024-02-23-linear-algebra-3/scaling.png){: w="50%" h="50%"}

$$
\begin{align*}&\mathbf{S}=\begin{bmatrix}0.5&0\\0&2\end{bmatrix}\quad[1, 1]\begin{bmatrix}0.5&0\\0&2\end{bmatrix}=[0.5, 2]\\&\mathbf{S}^{-1}=\begin{bmatrix}2&0\\0&0.5\end{bmatrix}\quad[-1, -2]\begin{bmatrix}2&0\\0&0.5\end{bmatrix}=[-2, -1]\end{align*}
$$

- $$\mathbf{S}$$: 가로는 0.5배, 세로는 2배 변형시키는 변환 행렬

### 이동(transition)

![move](/assets/img/2024-02-23-linear-algebra-3/move.png){: w="50%" h="50%"}
$$
\begin{align*}&x^\prime=x+b_x\\&y^\prime=y+b_y\end{align*}
$$


- $$x$$를 $$b_x$$만큼, $$y$$를 $$b_y$$만큼 이동

- 이동은 회전, 스케일링과 달리 선형 변환이 아님
  $$
  \begin{align*}
  \text{Function:}\quad&\tau(x, y, z) = (x + b_x, y + b_y, z + b_z) \\
  
  \text{Homogeneity:} \quad &\tau(ku_1, ku_2, ku_3) \\
  &= (ku_1 + b_x, ku_2 + b_y, ku_3 + b_z) \neq k \tau(u_1, u_2, u_3)
  \end{align*}
  $$

  - 계산해보면 두 조건 모두 만족하지 않음
  - 공간을 이동시키면 당연히 원점이 달라짐

- 애파인 변환(Affine Transpormation)을 이용하면 행렬로 표현할 수 있음
