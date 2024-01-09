---
title: 강화학습 Chapter 7. 가치 기반 에이전트
author: seyeon
date: 2024-01-09 01:00:00 +0900
categories: [AI, Reinforcement Learning]
tags: [AI, RL]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-01-09-reinforcement-learning-7/robot.jpg
  lqip: data:image/jpeg;base64,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
  alt: Robot
typora-root-url: ../
---

# 참고 자료

이 글은 [노승은, [바닥부터 배우는 강화 학습](https://shop.youngjin.com/goods/view?no=103), 영진닷컴(2020)]을 바탕으로 작성되었습니다.

# 가치 기반, 정책 기반, 액터-크리틱

![RL 에이전트의 분류](/assets/img/2024-01-09-reinforcement-learning-7/RL_Agent_types.png){: w="50%" h="50"}

## 가치 기반(value-based) 에이전트

- **가치 함수에 근거**하여 액션을 선택
  - 액션을 선택할 때 가치 함수만 있으면 되므로 **정책 함수가 따로 없음**
- [SARSA](/posts/reinforcement-learning-6/#2-td-컨트롤-1---sarsa)나 [Q러닝](/posts/reinforcement-learning-6/#3-td-컨트롤-2---q러닝)이 모두 가치 기반 에이전트에 해당

## 정책 기반(policy-based) 에이전트

- **정책 함수를 보고** 액션을 선택
  - 밸류를 보고 액션을 선택하지 않기 때문에 따로 가치 함수가 없음
- $$\pi$$를 이용해 MDP 안에서 경험을 쌓고 이를 이용해 $$\pi$$를 강화
  - 이 과정에서 가치 함수는 쓰이지 않고 가치를 평가하지도 않음

## 액터 크리틱(actor-critic)

- 가치 함수와 정책 함수를 **모두 사용**

# 1. 밸류 네트워크의 학습

![뉴럴넷으로 표현한 가치 함수](/assets/img/2024-01-09-reinforcement-learning-7/value_function_neural_net.png){: w="50%" h="50%"}

- 뉴럴넷으로 이루어진 가치 함수 $$v_\theta(s)$$를 **밸류 네트워크(value network)**라고 부름
  - 길이가 2인 벡터 인풋 $$s$$를 받아 정책 $$\pi$$를 따랐을 때의 밸류를 리턴
  - 정확히는 $$v_{\theta, \pi}(s)$$로 표현
- $$\theta$$: 뉴럴넷의 파라미터
  - 예) 파라미터가 100만개라면 $$\theta$$는 길이가 100만인 벡터
  - 처음에는 랜덤으로 초기화
  - 적절한 $$\theta$$를 찾아 각 상태에 맞는 밸류를 리턴하도록 하는 것이 목표

## 손실 함수

$$
L(\theta) = (v_{true}(s) - v_\theta(s))^2
$$

- 상태별 밸류의 값을 $$v_{true}(s)$$라고 가정
- 어떤 상태에 대해 $$L(\theta)$$를 최소화 할지 알 수 없음
  - 모든 상태를 방문하는 것은 현실적으로 거의 불가능 하기 때문에 계산하기 어려움

$$
L(\theta) = \mathbb{E}_\pi \left[ (v_{true}(s) - v_\theta(s))^2 \right]
$$

- 기댓값을 이용하여 **$$\pi$$를 통해 방문했던 $$s$$**에 대해서만 $$(v_{true}(s) - v_\theta(s))^2$$ 값을 계산하라는 의미

## 그라디언트

$$
\nabla_\theta L(\theta) = -\mathbb{E}_\pi \left[ (v_{true}(s) - v_\theta(s)) \nabla_\theta v_\theta(s) \right]
$$

- 앞에 곱해지는 $$2$$는 생략
  - 학습률 $$\alpha$$를 통해 조절할 수 있음

$$
\nabla_\theta L(\theta) \approx -(v_{true}(s) - v_\theta(s)) \nabla_\theta v_\theta(s)
$$

- $$\pi$$를 이용해 여러번 샘플을 뽑아 계산하면 결국 좌변과 우변은 거의 같아짐

$$
\begin{align}
\theta^\prime
& = \theta - \alpha \nabla_\theta L(\theta) \\
& = \theta + \alpha (v_{true}(s) - v_\theta(s)) \nabla_\theta v_\theta(s)
\end{align}
$$

- 모든 샘플에 대해 위 과정을 반복

## $$v_{true}(s)$$를 구하는 방법

### 1. 몬테카를로 리턴

$$
\begin{align}
& L(\theta) = \mathbb{E}_\pi \left[ (G_t - v_\theta(s_t))^2 \right] \\
& \theta^\prime = \theta + \alpha (G_t - v_\theta(s)) \nabla_\theta v_\theta(s)
\end{align}
$$

- 몬테카를로 학습처럼 가치 함수의 정의가 $$G_t$$의 기댓값이므로 대체 가능
- 에피소드가 끝나야 리턴을 계산할 수 있으므로 실시간 업데이트 불가

### 2. TD 타깃

$$
\begin{align}
& L(\theta) = \mathbb{E}_\pi \left[ (r_{t+1} + \gamma v_\theta(s_{t+1}) - v_\theta(s_t))^2 \right] \\
& \theta^\prime = \theta + \alpha (r_{t+1} + \gamma v_\theta(s_{t+1}) - v_\theta(s)) \nabla_\theta v_\theta(s)
\end{align}
$$

- $$r_{t+1} + \gamma v_\theta(s_{t+1})$$는 변수가 아닌 상수
- 매 스텝마다 실시간 업데이트 가능
