---
title: 강화학습 Chapter 8. 정책 기반 에이전트
author: seyeon
date: 2024-01-17 01:00:00 +0900
categories: [AI, Reinforcement Learning]
tags: [AI, RL]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-01-17-reinforcement-learning-8/robot.jpg
  lqip: data:image/jpeg;base64,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
  alt: Robot
typora-root-url: ../
---

# 참고 자료

이 글은 [노승은, [바닥부터 배우는 강화 학습](https://shop.youngjin.com/goods/view?no=103), 영진닷컴(2020)]을 바탕으로 작성되었습니다.

# 1. Policy Gradient

## 정책 기반 에이전트가 필요한 이유

### 확률적 정책

- 가치 기반 에이전트는 액션을 결정론적으로 선택
  - 모든 상태 $$s$$에 대해 각 상태에서 결정하는 액션이 고정
    - $$Q(s, a)$$가 가장 높은 액션을 선택
    - 학습이 끝났다면 $$Q(s, a)$$의 값은 고정되어 있으므로 선택하는 액션도 고정
  - 가위바위보를 할 때 계속 같은 것만 낸다면 상대가 전략을 수정해 쉽게 이길 수 있음
- 정책 기반 에이전트는 확률적 정책(stochastic policy)을 통해 다양한 액션을 선택
  - \$$\pi(s, a) = \mathbb{P}[a \mid s]$$
  - 가위바위보를 할 때 가위, 바위, 보를 동일한 확률로 선택하는 정책을 만들 수 있음

### 액션 공간이 연속적인 경우

- 0에서 1 사이의 모든 실수값이 액션으로 선택될 수 있는 경우
  - 가치 기반 에이전트는 모든 $$a$$에 대해 $$Q(s, a)$$의 값을 최대로 하는 $$a$$를 찾아야 함
  - 정책 기반 에이전트는 $$\pi(s)$$가 있다면 바로 액션을 선택할 수 있음

## 목적 함수 정하기

### 정책 네트워크

- \$$\pi_\theta(s, a)$$
  - 뉴럴넷을 이용하여 표현한 정책
  - $$\theta$$는 정책 네트워크의 파라미터

### 평가 함수

- \$$J(\theta)$$
  - 정책 네트워크 $$\pi_\theta(s, a)$$가 얼마나 좋은 정책인지 평가
  - $$\pi$$를 받아 점수를 반환
    - $$\pi$$는 $$\theta$$로 표현 가능하므로 $$\theta$$만 받아도 충분
  - 평가 함수의 값을 증가시키는 것, 즉 정책 네트워크를 강화시키는 것이 목표

$$
J(\theta) = \mathbb{E}_{\pi_\theta} \left[ \sum_t r_t \right] = v_{\pi_\theta}(s_0)
$$

- 보상의 합이 큰 정책이 좋은 정책이므로 보상의 합을 평가 함수라고 생각할 수 있음
  - 에피소드마다 다른 상태를 방문하기 때문에 기댓값 연산자가 필요
  
- 리턴의 기댓값을 가치 함수로 나타낼 수 있음
  - 만약 시작 상태가 $$s_0$$로 고정되어 있다면 $$s_0$$의 가치

    $$
    J(\theta) = \sum_{s \in S}d(s) \times v_{\pi_\theta}(s)
    $$

  - 시작 상태가 고정되어 있지 않다면 시작 상태의 확률 분포 $$d(s)$$를 이용하여 계산

$$
\theta^\prime = \theta + \alpha \times\nabla_\theta J(\theta)
$$

- 이 식을 실행하면 $$J(\theta^\prime)$$은 $$J(\theta)$$보다 커짐
- 이 과정을 반복하여 최적 정책의 파라미터 $$\theta^*$$를 찾는 방식을 그라디언트 어센트(gradient ascent)라고 부름

## 1-Step MDP

- 1-Step MDP: 1 스텝만 진행하고 에피소드가 끝나는 MDP
  - 처음 상태 $$s_0$$에서 액션 $$a$$를 선택하고 보상 $$R_{s, a}$$을 받고 끝남
  - 따라서 보상이 곧 리턴

$$
\begin{align}
J(\theta)
& = \sum_{s \in S}d(s) \times v_{\pi_\theta}(s)\\
& = \sum_{s \in S}d(s) \sum_{a \in A} \pi_\theta(s, a) \times R_{s, a}
\end{align}
$$

- $$s$$에서 모든 액션 $$a$$에 대해 $$a$$를 선택할 확률과 그 때 발생하는 보상의 곱을 모두 더해주면 $$s$$에서의 가치를 구할 수 있음

$$
\begin{align}
\nabla_\theta J(\theta)
& = \nabla_\theta \sum_{s \in S}d(s) \sum_{a \in A} \pi_\theta(s, a) \times R_{s, a} \\
& = \sum_{s \in S}d(s) \sum_{a \in A} \nabla_\theta \pi_\theta(s, a) \times R_{s, a} \\
& = \sum_{s \in S}d(s) \sum_{a \in A} \pi_\theta(s, a) \frac{\nabla_\theta \pi_\theta(s, a)}{\pi_\theta(s, a)} \times R_{s, a} \\
& = \sum_{s \in S}d(s) \sum_{a \in A} \pi_\theta(s, a) \nabla_\theta \ln{\pi_\theta(s, a)} \times R_{s, a} \quad \because d \ln{x} = \frac{d x}{x} \\
& = \mathbb{E}_{\pi_\theta} \left[ \nabla_\theta \ln{\pi_\theta(s, a)} \times R_{s, a} \right]
\end{align}
$$

- 기댓값 연산자 덕분에 샘플 기반 방법론을 사용할 수 있음
  - $$\pi_\theta(s, a)$$에 대한 기댓값이므로 에이전트를 환경에 놓고 $$\nabla_\theta \ln{\pi_\theta(s, a)} \times R_{s, a}$$의 값을 여러개 모으면 됨
    - $$\nabla_\theta \ln{\pi_\theta(s, a)}$$는 뉴럴넷의 그라디언트
    - $$R_{s, a}$$는 $$s$$에서 $$a$$를 선택하고 얻는 보상을 관측하여 수집

## 일반적 MDP에서의 Policy Gradient

$$
\nabla_\theta J(\theta) = \mathbb{E}_{\pi_\theta} \left[ \nabla_\theta \ln{\pi_\theta(s, a)} \times Q_{\pi_\theta}(s, a) \right]
$$

- 1-Step MDP에서의 식을 확장
  - $$R_{s, a}$$가 $$Q_{\pi_\theta}(s, a)$$로 바뀜
    - $$s$$에서 $$a$$를 선택했을 때 받는 보상 대신 $$s$$에서 $$a$$를 선택할 때 얻는 리턴의 기댓값으로 의미가 달라짐
    - 스텝이 여러개 있기 때문에 미래에 받을 보상까지 더해주는 개념

# 2. REINFORCE 알고리즘

## 이론적 배경

$$
\nabla_\theta J(\theta) = \mathbb{E}_{\pi_\theta} \left[ \nabla_\theta \ln{\pi_\theta(s, a)} \times G_t \right]
$$

- $$Q_{\pi_\theta}(s, a)$$ 대신 $$G_t$$로 바뀜
  - $$Q_\pi(s, a) = \mathbb{E}[G_t \mid s_t = s, a_t = a]$$이므로 $$G_t$$의 샘플을 여러개 구해 평균을 내면 $$Q_{\pi_\theta}(s, a)$$에 가까워짐

## REINFORCE pseudo code

1. $$\pi_\theta(s, a)$$의 파라미터 $$\theta$$를 랜덤으로 초기화
2. 다음 (1 ~ 3)을 반복
   1. 에이전트의 상태를 초기화: $$s \leftarrow  s_0$$
   2. $$\pi_\theta$$를 이용하여 에피소드 끝까지 진행하여 $$\{ s_0, a_0, r_0, s_1, a_1, r_1, ..., s_T, a_T, r_T \}$$를 획득
   3. $$t = 0 \sim T$$에 대해 다음을 반복
      - \$$G_t \leftarrow \sum_{i=t}^T r_i \times \gamma^{i-t}$$
      - \$$\theta \leftarrow \theta + \alpha \times \nabla_\theta \ln{\pi_\theta(s_t, a_t)} \times G_t$$

- 평가 함수에 로그(미분하면 항상 양수)가 포함되어 있기 때문에 $$G_t$$가 양수라면 증가, 음수라면 감소하게 됨

## REINFORCE 구현

$$
-G_t \times \ln{\pi_\theta (s_t, a_t)}
$$

- 평가 함수는 증가해야 하지만 라이브러리는 최소화하려 하기 때문에 $$-$$를 붙여줌
- 라이브러리가 알아서 최소값을 찾아주기 때문에 미분하기 이전 식을 사용
  - $$\theta$$에 대한 항이 $$\pi_\theta(s_t, a_t)$$ 하나이므로 $$\nabla$$ 연산자만 지우면 됨

### [Colab 링크](https://colab.research.google.com/drive/1QErRB4fQwH_CAzBvbFOge4TLC_4KIJD3#scrollTo=0VeKLDIhy82n)

### 라이브러리 import

``` python
import gym

import torch
import torch.nn as nn
import torch.nn.functional as F
import torch.optim as optim
from torch.distributions import Categorical
```

### 하이퍼 파라미터 정의

``` python
learning_rate = 0.0002
gamma = 0.98
```

### 정책 네트워크 클래스

``` python
class Policy(nn.Module):
    def __init__(self):
        super(Policy, self).__init__()
        self.data = []

        self.fc1 = nn.Linear(4, 128)
        self.relu1 = nn.ReLU()
        self.fc2 = nn.Linear(128, 2)
        self.softmax1 = nn.Softmax(dim=0)

        self.optimizer = optim.Adam(self.parameters(), lr=learning_rate)

    def forward(self, x):
        fc1 = self.fc1(x)
        relu1 = self.relu1(fc1)
        fc2 = self.fc2(relu1)
        softmax1 = self.softmax1(fc2)

        return softmax1

    def put_data(self, item):
        self.data.append(item)
    
    def train_net(self):
        R = 0
        self.optimizer.zero_grad()
        for r, prob in self.data[::-1]:
            R = r + gamma * R
            loss = -R * torch.log(prob)
            loss.backward()

        self.optimizer.step()
        self.data = []
```

### 메인 함수

``` python
def main():
    env = gym.make('CartPole-v1')
    pi = Policy()
    print_interval = 20
    score = 0.0
    best_pi = (0, pi.state_dict())

    for n_epi in range(10000):
        s = env.reset()
        done = False

        score = 0.0

        while not done:
            prob = pi(torch.from_numpy(s).float())
            m = Categorical(prob)
            a = m.sample()
            s_prime, r, done, info = env.step(a.item())
            pi.put_data((r, prob[a]))
            s = s_prime
            score += r
        
        pi.train_net()

        if score >= best_pi[0]:
            best_pi = (score, pi.state_dict())

        if (n_epi % print_interval == 0 and n_epi != 0):
            print("n_episode: {}, score: {:.1f}".format(n_epi, score))

        torch.save(pi.state_dict(), "./pi_final.pt")
        torch.save(best_pi[1], "./pi_best.pt")

main()
```

### 결과

![cartpole](/assets/img/2024-01-17-reinforcement-learning-8/cartpole_policy.gif)
