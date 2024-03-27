---
title: 자료구조 1. 자료구조와 빅오 표기법
author: seyeon
date: 2024-03-27 01:00:00 +0900
categories: [Computer Science, Data Structure]
tags: [data, structure]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-03-27-data-structure-1/data_structure_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Jigar Panchal
  
typora-root-url: ../
---

# 자료구조란?

- 효율적인 접근을 위해 자료를 보관하는 구조, 방법
- 책을 책장에 보관하는 방법
  - 아무런 규칙 없이 보관
    - 원하는 책을 찾을 때, 책장 전체를 하나하나 탐색
  - 가나다 순으로 보관
    - 원하는 책의 이름을 바탕으로 대략적인 위치를 예측 가능
  - 카테고리 별로 보관
    - 원하는 책의 카테고리에 해당하는 영역만 탐색
- 일상 생활과 자료구조 예시

  | 일상 생활에서의 예 | 자료구조             |
  | ------------------ | -------------------- |
  | 그릇을 쌓아서 보관 | 스택(stack)          |
  | 대기 줄            | 큐(queue)            |
  | 영어 사전          | 딕셔너리(dictionary) |
  | 컴퓨터 폴더 구조   | 트리(tree)           |
  | 지도               | 그래프(graph)        |

  - 이외에도 리스트(list), 해시(hash) 등 다양한 자료구조가 존재
- 상황에 맞는 자료구조를 선택하고 알고리즘과 조합해 프로그램을 만들 수 있음

# 추상 자료형(abstract data type, ADT)

- 구현 방법을 명시하지 않는 추상적 자료형
- 추상 자료형의 특징
  - 일종의 블랙박스(black box)로 사용자는 내부적으로 어떻게 동작하는지 알지 못해도 사용할 수 있음
  - 내부 구현이 변경되더라도 사용자는 이전 방식 그대로 사용할 수 있음
- TV와 비교
  - 사용자는 내부 구조(기계 회로)를 모르더라도 사용할 수 있음
  - 내부 장치(기계 부품)을 변경하더라도 이전과 같은 방식 그대로 사용할 수 있음

# 시간 복잡도(time complexity), 공간 복잡도(space complexity)

## 시간 복잡도

- 알고리즘의 연산이 대략적으로 몇 번 수행되는지를 의미
  - 일반적으로 반복문의 중첩으로 판단

- 입력의 개수(n)에 따른 연산 횟수를 $$T(n)$$처럼 함수로 나타냄
- 예)
  - $$n$$과 상관 없이 1번만 연산하는 알고리즘: $$T(n)=1$$
  - $$n$$번 연산하는 알고리즘: $$T(n)=n$$
  - $$n^2$$번 연산하는 알고리즘: $$T(n)=n^2$$

### 빅오 표기법(big-O notation)

- $$O(n)$$과 같이 표기
- 시간 복잡도 함수의 최고 차수만 나타내는 표기법
  - 정리: 두개의 함수 $$f(n)$$, $$g(n)$$이 주어졌을 때, $$n_0$$보다 큰 모든 $$n$$에 대하여 $$f(n)\le c g(n)$$인 $$c$$와 $$n_0$$가 존재하면 $$f(n)$$의 빅오 표기법은 $$O(g(n))$$

- 예) $$T(n)=n^2 + n + 1$$
  - $$n=1$$인 경우 $$T(n)=3$$이지만, $$n=1000$$인 경우 $$T(n)=1001001$$
  - 이처럼 $$n$$이 커질수록 최고 차항의 영향력이 압도적으로 증가
  - 따라서 빅오 표기법으로 나타내면 $$O(n^2)$$​
  - 정리: $$f(n)=T(n)$$이고 $$g(n)=n^2$$일 때, $$c=2$$, $$n_0=2$$라면 $$n^2+n+1 \le 2n^2$$를 만족하므로 $$O(n^2)$$

- 많이 쓰이는 빅오 표기법

  ![big-o graph](/assets/img/2024-03-27-data-structure-1/big-o_graph.png)

  - $$O(1)$$: 상수형(constant)
  - $$O(\log{n})$$: 로그형(logarithmic)
  - $$O(n)$$: 선형(linear)
  - $$O(n\log{n})$$: 선형로그형(log-linear)
  - $$O(n^2)$$: 2차형(quadratic)
  - $$O(n^3)$$: 3차형(polynomial...)
  - $$O(2^n)$$: 지수형(exponential)
  - $$O(n!)$$: 팩토리얼형(factorial)
- 빅오 표기법 cheat sheet([링크](https://www.bigocheatsheet.com/))
- 3개의 표기법 중 가장 많이 쓰임

  - 최악의 경우(상한)를 나타내기 때문


### 빅오메가 표기법(big-omega notation)

- 빅오 표기법의 정리에 따르면 $$f(n)=2n+1$$이어도 $$O(n^2)$$이라고 할 수도 있음
  - $$n_0=1$$, $$c=2$$라고 생각하면 $$2n+1 \le 2n^2$$이기 때문
- 이런 문제를 보완하기 위해 빅오메가 표기법을 사용
- 정리: 두개의 함수 $$f(n)$$, $$g(n)$$이 주어졌을 때, $$n_0$$보다 큰 모든 $$n$$에 대하여 $$f(n)\ge c g(n)$$인 $$c$$와 $$n_0$$가 존재하면 $$f(n)$$의 빅오메가 표기법은 $$\Omega(g(n))$$​
  - $$f(n)=2n+1$$인 경우, $$2n+1 \ge n$$이므로 $$\Omega(n)$$
- 하한을 나타냄

### 빅세타 표기법(big-theta notation)

- 정리: 두개의 함수 $$f(n)$$, $$g(n)$$이 주어졌을 때, $$n_0$$보다 큰 모든 $$n$$에 대하여 $$c_1 g(n)\le f(n)\le c_2 g(n)$$인 $$c_1$$, $$c_2$$와 $$n_0$$가 존재하면 $$f(n)$$의 빅세타 표기법은 $$\Theta(g(n))$$​
- 3개의 표기법 중 가장 정밀

