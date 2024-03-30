---
title: 자료구조 2. 재귀
author: seyeon
date: 2024-03-28 01:00:00 +0900
categories: [Computer Science, Data Structure]
tags: [data, structure]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-03-28-data-structure-2/data_structure_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Jigar Panchal
  
typora-root-url: ../
---

# 코드

- 모든 코드는 [깃허브](https://github.com/seyeon040768/data_structure)에서 확인하실 수 있습니다.

# 재귀(recursion)

- 자기 자신을 호출하여 문제를 해결하는 방법

- 수학적 귀납법과 비슷

- 예) 팩토리얼

  $$
  n! = 
  \begin{cases}
  1 & n=0\\
  n*(n-1)! & n \ge 1
  \end{cases}
  $$

  - $$5!$$은 $$5 \times (5 - 1)!$$으로 표현할 수 있고 다시 $$5 \times 4 \times (4 - 1)!$$, $$5 \times 4 \times 3 \times (3 - 1)!$$, $$5 \times 4 \times  3 \times 2 \times (2 - 1)!$$, $$5 \times 4 \times  3 \times 2 \times 1$$처럼 표현할 수 있음

## 재귀 함수

- 자기 자신을 호출하는 함수

- 예) 팩토리얼 함수

  ```c
  int FactorialRecursive(int n)
  {
  	if (n == 1)
  	{
  		return 1;
  	}
  
  	return n * FactorialRecursive(n - 1);
  }
  ```

- 재귀 함수의 필수 요소
  - 종료 조건
    - 종료 시점을 결정
    - 만약 없다면 계속 끝나지 않고 계속 호출됨(결국 런타임 에러 발생)
  - 재귀 호출
    - 재귀적으로 호출을 하지 않는다면 재귀 함수가 아님(당연)
- 재귀 함수 사고법

  - 함수를 완성하지 않았더라도 **‘이 함수는 이런 역할을 할거야’**라고 생각하고 사용

  - 큰 문제를 쪼개기

- 재귀 함수의 단점 및 주의점
  - 같은 계산을 여러번 할 수도 있음

    ```mermaid
      graph TD;
          fibo51["fibo(5)"] --> fibo41["fibo(4)"];
          fibo51 --> fibo31["fibo(3)"];
          fibo41 --> fibo32["fibo(3)"];
          fibo41 --> fibo21["fibo(2)"];
          fibo32 --> fibo22["fibo(2)"];
          fibo32 --> fibo11["fibo(1)"];
          fibo22 --> fibo12["fibo(1)"];
          fibo22 --> fibo01["fibo(0)"];
          fibo31 --> fibo23["fibo(2)"];
          fibo31 --> fibo13["fibo(1)"];
          fibo23 --> fibo14["fibo(1)"];
          fibo23 --> fibo02["fibo(0)"];
      
    ```

    - 피보나치 수열(1, 1, 2, 3, 5, 8, 13, ...)의 경우 위 그림처럼 같은 계산을 여러번 진행함
    - stack overflow가 발생할 수도 있음
    - 이러한 문제는 반복문을 사용하거나 다이나믹 프로그래밍 알고리즘을 통해 해결 가능
  - 캐싱 없이 간단한 반복문으로 해결할 수 있는 문제는 반복문 사용
    - 예) 1 ~ N까지 더하기, 팩토리얼 구하기
  - 그 외에는 우선 재귀 함수로 작성 후 필요한 경우 반복문으로 리팩토링
    - 재귀 함수를 사용하면 작성 속도가 빠르고 간편


## 재귀 함수를 이용한 하노이의 탑

### 하노이의 탑

![tower_of_hanoi](/assets/img/2024-03-28-data-structure-2/tower_of_hanoi.jpg)

- 브라흐마의 규칙
  - 한 번에 원판 하나씩만 옮길 수 있음
  - 작은 원판 위에 그보다 큰 원판이 올 수 없음
- 하노이의 탑
  - 막대가 3개 있음
  - 막대 하나에 n개의 원판으로 구성된 탑이 있음
  - 탑을 다른 막대에 이동시켜야 함

### 하노이의 탑 사고법

- 막대가 세 개가 있고, 한 막대에 n개의 원판이 있음
  - n개의 원판에서 상위 n-1개를 다른 막대에 옮길 수 있다고 가정
    - n-1개의 원판을 중간 막대로 옮김
    - 마지막 n번째 원판을 목적지 막대에 옮김
    - 중간 막대에 있던 n-1개의 원판을 목적지 막대에 옮김
- 막대가 세 개가 있고, 한 막대에 n-1개의 원판이 있음
  - n-1개의 원판에서 상위 n-2개를 다른 막대에 옮길 수 있다고 가정
    - n-2개의 원판을 중간 막대로 옮김
    - 마지막 n-1번째 원판을 목적지 막대에 옮김
    - 중간 막대에 있던 n-2개의 원판을 목적지 막대에 옮김
- 위와 같이 재귀적으로 생각하면 결국 마지막에는 1개의 원판을 이동시키는 문제가 됨
  - 이렇게 큰 문제를 작은 문제로 나눠 생각하면 간편함

### c언어 코드

- 코드

  ```c
  void TowerOfHanoiRecursive(int countDisc, char start, char temp, char end)
  {
  	if (countDisc == 1)
  	{
  		PrintMovingDisc(countDisc, start, end);
  
  		return;
  	}
  
  	TowerOfHanoiRecursive(countDisc - 1, start, end, temp);
  	PrintMovingDisc(countDisc, start, end);
  	TowerOfHanoiRecursive(countDisc - 1, temp, start, end);
  }
  ```

- 결과

  ```
  1: A -> B
  2: A -> C
  1: B -> C
  3: A -> B
  1: C -> A
  2: C -> B
  1: A -> B
  4: A -> C
  1: B -> C
  2: B -> A
  1: C -> A
  3: B -> C
  1: A -> B
  2: A -> C
  1: B -> C
  ```

  
