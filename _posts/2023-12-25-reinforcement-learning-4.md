---
title: 강화학습 Chapter 4. MDP를 알 때의 플래닝
author: seyeon
date: 2023-12-25 17:00:00 +0900
categories: [AI, Reinforcement Learning]
tags: [AI, RL]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2023-12-25-reinforcement-learning-4/robot.jpg
  lqip: data:image/jpeg;base64,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
  alt: Robot
typora-root-url: ../
---

# 참고 자료

이 글은 [노승은, [바닥부터 배우는 강화 학습](https://shop.youngjin.com/goods/view?no=103), 영진닷컴(2020)]을 바탕으로 작성되었습니다.

# MDP를 알 때의 플래닝

- 이번 챕터에서 다룰 내용의 전제 조건
  1. **작은 문제**
     - 상태 집합 $$S$$나 액션 집합 $$A$$의 크기가 작은 경우
  2. **MDP를 알고 있음**
     - 보상 함수와 전이 확률 행렬을 알고 있음
- **플래닝(planning)**: **MDP에 대한 모든 정보를 알 때** 이를 이용하여 정책을 개선하는 과정
- **테이블 기반 방법론(tabular method)**
  - 모든 상태 $$s$$나 상태와 액션의 페어 $$(s, a)$$에 대한 테이블을 생성
  - **테이블의 값을 업데이트하며 반복**
  - 작은 문제일 때 주로 사용

# 1. 밸류 평가하기 - 반복적 정책 평가

- **반복적 정책 평가(Iterative policy evaluation)**
  1. 테이블의 값 초기화
  2. 벨만 기대 방정식을 이용해 테이블의 값을 조금씩 업데이트

## 그리드 월드 예시

![그리드 월드](/assets/img/2023-12-25-reinforcement-learning-4/grid_world.png){: w="50%" h="50%"}

### 1. 테이블 초기화

![테이블 초기화](/assets/img/2023-12-25-reinforcement-learning-4/grid_init.png){: w="50%" h="50%"}

- 테이블에 상태별 밸류 $$v(s)$$를 기록하기 때문에 상태 $$s$$의 개수만큼의 빈칸이 필요
  - 이번 예시에서는 상태가 16개
- 어떤 값으로 초기화 해도 상관 없음
  - 적당한 값인 0으로 초기화

### 2. 상태의 값을 업데이트

![한 상태의 값을 업데이트](/assets/img/2023-12-25-reinforcement-learning-4/grid_update_1.png){: w="50%" h="50%"}

- $$s_5$$의 다음 상태가 될 후보는 동서남북 4칸($$s_1$$, $$s_4$$, $$s_6$$, $$s_9$$)

- $$r_s^a$$와 $$P_{ss^\prime}^a$$를 알기 때문에 **벨만 기대 방정식**을 사용하여 밸류를 구할 수 있음

  $$
  v_\pi(s) = \sum_{a\in A} \pi(a\mid s) \left( r_s^a + \gamma \sum_{s^\prime \in S} P_{ss^\prime}^a v_\pi (s^\prime) \right)
  $$

  - 4방향 랜덤이므로 $$\pi(a \mid s)$$는 0.25

  - 보상 $$r_s^a$$는 -1

  - $$\gamma$$는 1로 계산

  - $$\pi(a \mid s)$$를 통해 동서남북 중 어느 방향으로 이동할지 액션을 정하고 실행하면 **무조건 해당 상태에 도착**하므로 $$P_{ss^\prime}^a$$는 1

    $$
    \begin{align}
    v_{pi}(s_5) = \;
       & 0.25 \times(-1 + 1 \times (1 \times 0.0)) + 0.25 \times(-1 + 1 \times (1 \times 0.0)) \\
       & + 0.25 \times(-1 + 1 \times (1 \times 0.0)) + 0.25 \times(-1 + 1 \times (1 \times 0.0))
       = -1.0
    \end{align}
    $$

![모든 상태의 값을 업데이트](/assets/img/2023-12-25-reinforcement-learning-4/grid_update_all.png){: w="20%" h="20%"}

- 종료 상태를 제외한 모든 상태에 대해 밸류를 계산
  - 업데이트 할 때는 새로 업데이트 된 밸류가 아닌 업데이트 이전의 값을 사용
    - $$s_5$$를 업데이트하고 $$s_6$$를 업데이트 할 때, 업데이트 된 $$s_5$$의 밸류인 -1.0이 아닌 이전 $$s_5$$의 밸류인 0.0을 사용
  - 종료 상태의 밸류는 0

### 3. [과정 2](#2-상태의-값을-업데이트)를 반복

![값이 수렴할 때까지 반복](/assets/img/2023-12-25-reinforcement-learning-4/grid_repeat_update.png){: w="70%" h="70%"}

- 계속 반복하면 어떤 값에 수렴
  > 항상 수렴하는 이유 [참고](https://www.andrew.cmu.edu/course/10-703/slides/lecture4_valuePolicyDP-9-10-2018.pdf)
  {: .prompt-info}

- 반복된 업데이트를 통해 각 상태의 실제 가치를 알 수 있음
  - $$s_0$$의 밸류는 -59.4로 무작위로 움직일 때 대락 60번 움직여야 종료 상태에 도착한다는 의미

# 2. 최고의 정책 찾기 - 정책 이터레이션

## 평가와 개선의 반복

![정책 이터레이션](/assets/img/2023-12-25-reinforcement-learning-4/policy_iteration.png){: w="50%" h="50%"}

### 정책 평가(policy evaluation)

- 고정된 $$\pi$$에 대한 **각 상태의 밸류 계산**
- [반복적 정책 평가](#1-밸류-평가하기---반복적-정책-평가) 사용

### 정책 개선(policy improvement)

- **새로운 정책 $$\pi^\prime$$ 생성**
- [정책 평가](#정책-평가policy-evaluation)에서 구한 $$v(s)$$에 대한 그리디 정책을 생성

<br/>

- 정책 평가와 정책 개선을 계속 반복하다보면 정책과 그에 따른 가치 모두 변하지 않는 단계에 도달
  - 도달한 곳의 정책과 가치가 바로 **최적 정책**과 **최적 가치**

### 그리드 월드 예시

![각 상태의 가치와 그에 따른 그리디 정책](/assets/img/2023-12-25-reinforcement-learning-4/eval_and_improve.png){: w="50%" h="50%"}

- $$s_5$$에서 가치를 높일 수 있는 액션은 $$a_남$$과 $$a_동$$
  - 따라서 $$\pi^\prime (a_동 \mid s_5) = 1.0 \; or \; \pi^\prime (a_남 \mid s_5) = 1.0$$과 같은 정책을 생각해 볼 수 있음
  - 이렇게 눈 앞의 이익을 최대화 하는 선택을 하는 정책을 **그리디 정책(greedy policy)**이라고 함

- 각 상태에 대해 **그리디 정책을 계산하면 더 좋은 정책을 얻을 수 있음**

> 예시에서는 한 번만 그리디 정책을 계산해 최적 정책을 얻었지만 실제로 이런 경우는 별로 없음
{: .prompt-warning}

### 정책이 반드시 개선되는 이유

- $$\pi_{greedy}$$: 딱 한 칸($$s$$)만 그리디 정책으로 움직이고 나머지는 원래 정책 $$\pi$$을 따르는 정책
  - 반드시 $$\pi_{greedy} \gt \pi$$
- 귀납적으로 적용하면 $$s$$ 다음 칸에서도 그리디하게 움직이는게 좋고, 또 다음 칸에서도 좋음
- 따라서 모든 상태에서 그리디한 정책이 원래 정책보다 좋음

## 정책 평가 간소화

![정책 이터레이션 도식](/assets/img/2023-12-25-reinforcement-learning-4/policy_iter_non_optim.png){: w="50%" h="50%"}

- 세로로 이어지는 루프(정책 이터레이션) 안에 가로로 이어지는 루프(정책 평가)가 포함되어 있음
  - 따라서 **복잡하고 느릴 수도 있음**

![업데이트 횟수와 그에 따른 그리디 정책](/assets/img/2023-12-25-reinforcement-learning-4/compare_greedy_policy.png){: w="50%" h="50%"}

- 반복적 정책 평가를 수렴할 때까지 하지 않고 일찍 멈춰(early stopping)도 최적 정책을 구할 수 있음
  - **가치 평가를 수렴할 때까지 하지 않아도 된다**는 것을 알 수 있음

![간결해진 정책 이터레이션](/assets/img/2023-12-25-reinforcement-learning-4/early_stopping.png){: w="20%" h="20%"}

- 이렇게 하면 **간결하고 빠르게** 최적 정책을 찾을 수 있음
