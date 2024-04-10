---
title: 이산수학 5. 행렬
author: seyeon
date: 2024-04-05 01:00:00 +0900
categories: [Math, Discrete Mathematics]
tags: [discrete]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-04-05-discrete-mathematics-5/discrete_mathematics_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Philip Oroni
  
typora-root-url: ../
---

# 1. 행렬의 개념

- 행렬(matrix, $$A=[a_{ij}]$$): 하나 이상의 원소를 1차원 또는 2차원의 행태로 나열한 것

  $$
  A = 
  \begin{bmatrix}
  a_{11} & a_{12} & \cdots & a_{1n} \\
  a_{21} & a_{22} & \cdots & a_{2n} \\
  \vdots & \vdots & \ddots & \vdots \\
  a_{m1} & a_{m2} & \cdots & a_{mn} \\
  \end{bmatrix}
  $$

  - $$a_{ij}$$: 행렬의 $$i$$번째 행, $$j$$번째 열에 위치한 원소
  - 행(row): 가로줄
  - 열(column): 세로줄
- 영행렬(zero matrix, $$O$$): 모든 원소가 $$0$$인 행렬
- $$n$$차 정사각행렬($$n$$-square matrix): $$n \times n$$ 모양의 행렬
  - 주대각원소(main diagonal element): 원소 $$a_{ij}$$ 중 $$i = j$$인 원소
- 단위행렬(identity matrix, $$I$$): 주대각원소만 $$1$$이고 나머지 원소는 모두 $$0$$​인 정사각행렬

  $$
  I = 
  \begin{bmatrix}
  1 & 0 & \cdots & 0 \\
  0 & 1 & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & 1 \\
  \end{bmatrix}
  $$

# 2. 행렬의 연산

- 덧셈과 뺄셈: 같은 위치에 있는 원소끼리 연산, $$A + B = [a_{ij} + b_{ij}]$$

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

  - 따라서 모양이 다른 두 행렬은 서로 더하거나 뺄 수 없음
- 스칼라곱: 각 원소에 스칼라 값을 곱셈, $$kA = [ka_{ij}]$$
- 곱셈: 앞 행렬의 행과 뒤 행렬의 열을 곱셈

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
    - $$a\times b$$ 크기의 행렬과 $$b\times c$$ 크기의 행렬을 곱한 행렬의 크기는 $$a\times c$$
  - 행렬 곱은 순서가 바뀌면 결과가 달라지거나 모양이 달라 곱할 수 없음
  - 곱셈의 성질
    - \$(AB)C = A(BC)$
    - \$AI = IA = A$

# 3. 행렬의 종류

- 대각행렬(diagonal matrix): $$n$$차 정사각행렬에서 주대각원소를 제외한 나머지 원소가 모두 $$0$$인 행렬
  $$
  A = 
  \begin{bmatrix}
  a_{11} & 0 & \cdots & 0 \\
  0 & a_{22} & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & a_{nn} \\
  \end{bmatrix}
  $$

- 전치행렬(transpose matrix, $$A^T$$): 행렬의 행과 열을 교환한 행렬
    - 위첨자 $$T$$를 이용해 표기
    - 주대각선을 기준으로 뒤집은 형태

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

- 대칭행렬(symmetric matrix): 정사각행렬 $$A$$에 대해 $$A^T = A$$인 행렬
- 부울행렬(boolean matrix): 모든 원소가 $$0$$($$F$$)과 $$1$$($$T$$)로만 구성된 행렬
  - 부울행렬 연산자
    - 합(join): $$A \lor B = [a_{ij} \lor b_{ij}]$$
    - 교차(meet): $$A \land B = [a_{ij} \land b_{ij}]$$
    - 부울곱(boolean product): $$A \odot B = [(a_{i1} \land b_{ij}) \lor (a_{i2} \land b_{2j}) \lor \cdots \lor (a_{im} \land b_{mj})]$$
      - 행렬곱에서 $$\times$$ 대신 $$\land$$를, $$+$$ 대신 $$\lor$$를 수행

# 4. 행렬식

- 소행렬(minor matrix, $$M_{ij}$$): $$n$$차 정사각행렬에서 $$i$$행과 $$j$$열을 제거해서 얻은 $$n-1$$​차 정사각행렬
  - 예)

    $$
    \begin{align*}&\mathbf{\bar{A}}_{11}=\left[\begin{matrix}A_{22}&A_{23}\\A_{32}&A_{33}\end{matrix}\right]\\&\mathbf{\bar{A}}_{22}=\left[\begin{matrix}A_{11}&A_{13}\\A_{31}&A_{33}\end{matrix}\right]\\&\mathbf{\bar{A}}_{13}=\left[\begin{matrix}A_{21}&A_{22}\\A_{31}&A_{32}\end{matrix}\right]\end{align*}
    $$

- 행렬식(determinant, $$\det{A}$$​​)

  $$
  \det{\mathbf{A}}=\sum_{j=1}^n A_{1j}(-1)^{1+j}\det{\mathbf{\bar{A}}_{1j}}
  $$

  - $$n$$: 열의 개수
  - $$A_{1j}$$: 첫번째 행의 각 원소
  - $$(-1)^{1+j}$$: 홀수번째 열이면 양수, 짝수번째 열이면 음수
  - $$\det{\mathbf{\bar{A}}_{1j}}$$: 첫번째 행의 각 원소에 대한 소행렬의 행렬식
  - 예)

    $$
    \det{\left[\begin{matrix}A_{11}&A_{12}\\A_{21}&A_{22}\end{matrix}\right]}=A_{11}\det{\left[A_{22}\right]}-A_{12}\det{\left[A_{21}\right]}=A_{11}A_{22}-A_{12}A_{21}
    $$
    
  - 3x3 이상 행렬의 determinant는 재귀적으로 계산
- 여인수 행렬(cofactor matrix: $$[C_{ij}]$$)

  $$
  \mathbf{C_A}=[C_{ij}]=[(-1)^{i+j}\det{\mathbf{\bar{A}}_{ij}}]=\left[\begin{matrix} C_{11} & C_{12} & \dots & C_{1n} \\ C_{21} &   C_{22} & \dots & C_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ C_{n1}   & C_{n2} & \dots & C_{nn} \end{matrix}\right]
  $$

# 5. 역행렬

- 역행렬(inverse matrix, $$A^{-1}$$): 정사각행렬 $$A$$에 대하여, $$AB = BA = I$$를 만족하는 행렬 $$B$$

  $$
  AA^{-1} = A^{-1}A = I
  $$

- 수반 행렬(adjoint matrix, $$[A_{ij}]^T$$): 여인수 행렬의 전치

  $$
  \mathbf{A}^\ast=\mathbf{C}_\mathbf{A}^T
  $$

- 수반 행렬을 이용한 역행렬 계산

  $$
  \mathbf{A}^{-1}=\frac{\mathbf{A}^\ast}{\det{\mathbf{A}}}
  $$

- 가역행렬(invertible matrix): 역행렬이 존재하는 행렬, $$\det{A} \neq 0$$
- 특이 행렬(singular matrix): 역행렬이 존재하지 않는 행렬, $$\det{A} = 0$$

# 6. 행렬과 연립일차방정식

- 일차방정식(linear equation): $$a_1x_1 + a_2x_2 + \cdots + a_nx_n = b$$

- 해집합(solution set): 방정식을 참으로 만드는 변수들의 집합

- 연립일차방정식(system of linear equations): $$m$$개의 일차방정식으로 구성된 방정식

  $$
  \begin{cases}
  a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1\\
  a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = b_1\\
  \cdots\\
  a_{m1}x_1 + a_{m2}x_2 + \cdots + a_{mn}x_n = b_m\\
  \end{cases}
  $$

- 계수 행렬(coefficient matrix): 연립일차방정식의 계수들로 구성된 $$m \times n$$ 행렬
  $$
  A =
  \begin{bmatrix}
  a_{11} & a_{12} & \cdots & a_{1n}\\
  a_{21} & a_{22} & \cdots & a_{2n}\\
  \vdots & \vdots & \ddots & \vdots\\
  a_{m1} & a_{m2} & \cdots & a_{mn}\\
  \end{bmatrix}
  $$

- 미지수 행렬(unknown value matrix): 연립일차방정식의 미지수들로 구성된 $$n \times 1$$ 행렬

  $$
  X = \begin{bmatrix} x_1\\ x_2\\ \vdots\\ x_n\\ \end{bmatrix}
  $$
  
- 상수 행렬(constant matrix): 연립일차방정식의 상수들로 구성된 $$m \times 1$$ 행렬

  $$
  B = \begin{bmatrix} b_1\\ b_2\\ \vdots\\ b_m\\ \end{bmatrix}
  $$

- 계수 행렬, 미지수 행렬, 상수 행렬을 이용해 연립일차방정식을 표현할 수 있음

  $$
  AX = \begin{bmatrix}
  a_{11} & a_{12} & \cdots & a_{1n}\\
  a_{21} & a_{22} & \cdots & a_{2n}\\
  \vdots & \vdots & \ddots & \vdots\\
  a_{m1} & a_{m2} & \cdots & a_{mn}\\
  \end{bmatrix} \begin{bmatrix} x_1\\ x_2\\ \vdots\\ x_n\\ \end{bmatrix} = \begin{bmatrix} b_1\\ b_2\\ \vdots\\ b_m\\ \end{bmatrix} = B
  $$
  
- 첨가행렬(augmented matrix): 계수 행렬과 상수 행렬을 다음과 같이 표현한 행렬

  $$
  \left[
  \begin{array}{cccc|c}
  a_{11} & a_{12} & \cdots & a_{1n} & b_1\\
  a_{21} & a_{22} & \cdots & a_{2n} & b_2\\
  \vdots & \vdots & \ddots & \vdots & \vdots\\
  a_{m1} & a_{m2} & \cdots & a_{mn} & b_m\\
  \end{array}
  \right]
  $$

- 행 사다리꼴 행렬(row echelon form matrix): 각 행의 $$0$$이 아닌 첫 번째 원소가 $$1$$이고, 그 $$1$$을 포함하는 열에서 $$1$$의 아래쪽 원소가 모두 $$0$$​​인 행렬
  
  - 조건
  
    1. 어떤 행은 1열부터 $$0$$으로 시작
    2. 모든 행의 $$0$$이 아닌 첫 번째 원소는 $$1$$
    3. 모든 행의 $$0$$이 아닌 첫 번째 원소는 상위 행의 $$0$$이 아닌 첫 번째 원소보다 오른쪽 열에 위치
    4. 모든 원소가 $$0$$인 행이 있다면 행렬의 가장 마지막 행에 위치
  
  - 예)

    $$
    \begin{bmatrix}
    1 & a & b & c\\
    0 & 1 & d & e\\
    0 & 0 & 0 & 1\\
    \end{bmatrix}
    $$
  
- 기약 행 사다리꼴 행렬(reduced row echelon form matrix): 행 사다리꼴 행렬에서 각 행의 $$0$$이 아닌 첫 번째 원소 $$1$$을 포함한 열의 나머지 원소가 모두 $$0$$인 행렬
  - 예)

    $$
    \begin{bmatrix}
    1 & 0 & a & 0\\
    0 & 1 & b & 0\\
    0 & 0 & 0 & 1\\
    \end{bmatrix}
    $$

## 가우스 소거법

- 후진대입법

  $$
  \begin{cases}
  x_1 + x_2 + x_3 = b_1\\
  x_2 + x_3 = b_2\\
  x_3 = b_3\\
  \end{cases}
  $$
  
  - 3번째 식의 $$x_3$$을 2번째 식에 대입
  - 2번째 식의 $$x_2$$​를 1번째 식에 대입

- 기본 행 연산(elementary row operation)

  - 한 행에 $$0$$이 아닌 스칼라를 곱한다.
  - 스칼라곱을 한 행을 다른 행에 더한다.
  - 필요에 따라 행의 위치 교환 가능


## 가우스 조단 소거법

- 기약 행 사다리꼴 행렬을 만들어 해를 구하는 방법

  - 기본 행 연산을 이용
  
  $$
  \left[\begin{array}{cccc|c}
  a_{11} & a_{12} & \cdots & a_{1n} & b_1 \\
  a_{21} & a_{22} & \cdots & a_{2n} & b_2 \\
  \vdots & \vdots & \ddots & \vdots & \vdots \\
  a_{m1} & a_{m2} & \cdots & a_{mn}  & b_m\\
  \end{array}\right]
  \xrightarrow{\text{Gauss-Jordan}}
  \left[\begin{array}{cccc|c}
  1 & 0 & \cdots & 0 & x_1 \\
  0 & 1 & \cdots & 0 & x_2 \\
  \vdots & \vdots & \ddots & \vdots & \vdots \\
  0 & 0 & \cdots & 1 & x_n\\
  \end{array}\right]
  $$

- 가우스 조단 소거법을 이용한 역행렬 계산
  $$
  \left[\begin{array}{cccc|cccc}
  a_{11} & a_{12} & \cdots & a_{1n} & 1 & 0 & \cdots & 0 \\
  a_{21} & a_{22} & \cdots & a_{2n} & 0 & 1 & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots & \vdots & \vdots & \ddots & \vdots \\
  a_{m1} & a_{m2} & \cdots & a_{mn} & 0 & 0 & \cdots & 1 \\
  \end{array}\right]
  \xrightarrow{\text{Gauss-Jordan}}
  \left[\begin{array}{cccc|cccc}
  1 & 0 & \cdots & 0 & a^{\prime}_{11} & a^{\prime}_{12} & \cdots & a^{\prime}_{1n} \\
  0 & 1 & \cdots & 0 & a^{\prime}_{21} & a^{\prime}_{22} & \cdots & a^{\prime}_{2n} \\
  \vdots & \vdots & \ddots & \vdots & \vdots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & 1 & a^{\prime}_{m1} & a^{\prime}_{m2} & \cdots & a^{\prime}_{mn} \\
  \end{array}\right]
  $$

  - 첨가행렬의 우측에 단위행렬을 넣고 가우스 조단 소거법을 이용해 좌측 행렬을 단위행렬로 만들면 우측 행렬이 역행렬이 됨
  - $$A = [a_{ij}]$$의 역행렬은 $$A^{-1}=[a^{\prime}_{ij}]$$