---
title: 강화학습 Chapter 3. 벨만 방정식
author: seyeon
date: 2023-12-24 02:17:00 +0900
categories: [AI, Reinforcement Learning]
tags: [AI, RL]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2023-12-24-reinforcement-learning-3/robot.jpg
  lqip: data:image/jpeg;base64,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
  alt: Robot
typora-root-url: ../
---

# 참고 자료

이 글은 [노승은, [바닥부터 배우는 강화 학습](https://shop.youngjin.com/goods/view?no=103), 영진닷컴(2022)]을 바탕으로 작성되었습니다.

# 벨만 방정식(Bellman Equation)

- 주어진 상태의 밸류를 계산하는 방정식
- 재귀적 관계를 이용
  - 시점 $$r$$과 $$r + 1$$ 사이의 관계를 이용

# 1. 벨만 기대 방정식(Bellman Expectation Equation)

## 0단계

$$
\begin{align}
& v_\pi(s_t) = \mathbb{E}_\pi[r_{r+1} + \gamma v_\pi(s_{t+1})] \\
& q_\pi(s_t, a_t) = \mathbb{E}_\pi[r_{r+1} + \gamma q_\pi(s_{t+1}, a_{t+1})]
\end{align}
$$

### 증명

$$
\begin{align}
v_\pi(s_t) & = \mathbb{E}_\pi[G_t] \\
& = \mathbb{E}_\pi[r_{t+1}+\gamma r_{r+2} + \gamma^2 r_{r+3} + \cdots] \\
& = \mathbb{E}_\pi[r_{t+1}+\gamma (r_{r+2} + \gamma r_{r+3} + \cdots)] \\
& = \mathbb{E}_\pi[r_{t+1}+\gamma G_{t+1}] \\
& = \mathbb{E}_\pi[r_{t+1}+\gamma v_\pi (s_{t+1})]
\end{align}
$$

- $$q_\pi(s_t, a_t) = \mathbb{E}_\pi[r_{r+1} + \gamma q_\pi(s_{t+1}, a_{t+1})]$$도 같은 방식으로 증명 가능

### 퀴즈

1. $$v_\pi(s_t) = r_{r+1} + \gamma v_\pi(s_{t+1})$$가 성립한다
   - 답은 X
   - $$s_t$$에서 $$s_{t+1}$$이 정해지기까지 **두 번의 확률 과정**을 거쳐야 함
     - 정책이 액션을 선택($$\pi$$에 의한 선택)
     - 전이 확률이 다음 상태를 선택($$P_{s_t, s_{t+1}}^{a_{t}}$$에 의한 선택)
   - 다음 시점에 **어떤 상태에 도달할 지 모르기 때문**에 반드시 **기댓값**을 사용해야 함
2. \$$v_\pi(s_t)= \mathbb{E}_\pi[r_{t+1}+\gamma r_{r+2} + \gamma^2 v_\pi (x_{t+2})]$$
   - 답은 O
   - 재귀적으로 당연함

## 1단계

### $$q_\pi$$를 이용해 $$v_\pi$$ 계산하기

$$
v_\pi(s) = \sum_{a\in A} \pi(a\mid s)q_\pi (s, a)
$$

- $$s$$에서의 밸류 = ($$s$$에서 $$a$$를 실행할 확률 * $$s$$에서  $$a$$를 실행하는 것의 밸류)들의 합

- 예)

  ![액션 밸류로 상태 밸류 계산하기](/assets/img/2023-12-24-reinforcement-learning-3/step1_1_example.png){: w="50%" h="50%"}
  

<br/>

$$
\begin{align}
  v_\pi(s) & = \pi(a_1 \mid s) \times q_\pi(s, a_1) + \pi(a_2 \mid s) \times q_\pi(s, a_2) \\
  & = 0.6 \times 1 + 0.4 \times 2 \\
  & = 1.4
  \end{align}
$$

### $$v_\pi$$를 이용해 $$q_\pi$$ 계산하기

$$
q_\pi(s, a) = r_s^a + \gamma \sum_{s^\prime \in S} P_{ss^\prime}^a v_\pi (s^\prime)
$$

- $$s$$에서 $$a$$를 실행하는 것의 밸류 = $$s$$에서 $$a$$를 실행할 때의 보상(즉시 얻는 보상) + 감쇠 인자 * ($$s$$에서 $$a$$를 실행하면 $$s^\prime$$에 도착할 확률 * $$s^\prime$$의 밸류)들의 합

- 예)

  ![상태 밸류로 액션 밸류 계산하기](/assets/img/2023-12-24-reinforcement-learning-3/step1_2_example.png){: w="50%" h="50%"}
  

<br/>

$$
\begin{align}
q_\pi (s, a_1) & = r_s^{a_1} + P_{ss_1}^a \times v_\pi(s_1) + P_{ss_2}^a \times v_\pi(s_2) \\
& = 0.5 + 0.7 \times 1.5 + 0.3 \times (-1) \\
& = 1.25
\end{align}
$$

## 2단계

$$
\begin{align}
&
v_\pi(s) = \sum_{a\in A} \pi(a\mid s)q_\pi (s, a) = \sum_{a\in A} \pi(a\mid s) \left( r_s^a + \gamma \sum_{s^\prime \in S} P_{ss^\prime}^a v_\pi (s^\prime) \right)  \quad
\because q_\pi(s, a) = r_s^a + \gamma \sum_{s^\prime \in S} P_{ss^\prime}^a v_\pi (s^\prime) \\

&
q_\pi(s, a) = r_s^a + \gamma \sum_{s^\prime \in S} P_{ss^\prime}^a v_\pi (s^\prime) = r_s^a + \gamma \sum_{s^\prime \in S} P_{ss^\prime}^a \sum_{a^\prime\in A} \pi(a^\prime \mid s^\prime)q_\pi (s^\prime, a^\prime) \quad
\because v_\pi(s^\prime) = \sum_{a^\prime\in A} \pi(a^\prime \mid s^\prime)q_\pi (s^\prime, a^\prime)
\end{align}
$$

- [1단계](#1단계)에서 구한 $$q_\pi(s, a)$$와 $$v_\pi(s)$$를 대입

### [0단계](#0단계)와의 비교

- 0단계: $$v_\pi(s_t) = \mathbb{E}_\pi[r_{r+1} + \gamma v_\pi(s_{t+1})]$$
- 2단계: $$v_\pi(s) = \sum_{a\in A} \pi(a\mid s) \left( r_s^a + \gamma \sum_{s^\prime \in S} P_{ss^\prime}^a v_\pi (s^\prime) \right)$$ 
  - 2단계는 0단계의 **기댓값 연산자를 확률과 밸류의 곱 형태로 풀어서 쓴 형태**
- 2단계를 계산하기 위해서는 $$r_s^a$$와 $$P_{ss^\prime}^a$$를 반드시 알아야 함
  - 하지만 $$r_s^a$$와 $$P_{ss^\prime}^a$$는 환경의 일부
    - $$r_s^a$$를 미리 알고 있다는 것은 $$s$$에서 $$a$$를 했을 때 얼마의 보상을 받을지 기댓값을 안다는 뜻
    - $$P_{ss^\prime}^a$$를 미리 알고 있다는 것은 $$s$$에서 $$a$$를 했을 때 어떤 상태에 도달할지 확률 분포를 알고 있다는 뜻
    - 하지만 $$s$$에서 $$a$$를 해보기도 전에 미리 $$r_s^a$$와 $$P_{ss^\prime}^a$$를 아는 것은 매우 어려움
  - $$r_s^a$$와 $$P_{ss^\prime}^a$$를 알 때 **"MDP를 안다"**고 표현
- **모델-프리(model-free) 접근법**: MDP를 모를 때 경험하며 학습하는 접근법
- **모델-기반(model-based) 접근법** 또는 **플래닝(planning)**: MDP를 알 때 학습하는 접근법
