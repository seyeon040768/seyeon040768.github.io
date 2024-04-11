---
title: 강화학습 Chapter 2. 마르코프 결정 프로세스(Markov Decision Process)
author: seyeon
date: 2023-12-22 23:00:00 +0900
categories: [Artificial Intelligence, Reinforcement Learning]
tags: [AI, RL]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2023-12-22-reinforcement-learning-2/robot.jpg
  lqip: data:image/jpeg;base64,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
  alt: Robot
typora-root-url: ../
---

# 참고 자료

이 글은 [노승은, [바닥부터 배우는 강화 학습](https://shop.youngjin.com/goods/view?no=103), 영진닷컴(2020)]을 바탕으로 작성되었습니다.



# 1. 마르코프 프로세스(Markov Process)

## 마르코프 성질(Markov property)

- 미래는 오직 **현재에 의해 결정**된다는 성질
  $$
  \mathbb{P}[s_{t+1}\mid s_t] = \mathbb{P}[s_{t+1}\mid s_0, s_1, ..., s_{t-1}, s_t]
  $$

  - 마르코프한 상태
    - 체스: 현재 상황이 가장 중요, 이전에 어떤 상태를 거쳐 현재에 도달했는지는 중요하지 않음
  - 마르코프하지 않은 상태
    - 운전(특정 시점의 사진): 지금 앞으로 가는지, 뒤로 가는지 조차 알기 어려움
    - 현재 뿐만 아니라 이전 상태의 정보(1, 2, 3초전의 사진)나 현재 상태에 대한 더 많은 정보(속도, 가속도)를 통해 조금이라도 더 마르코프하게 만들 수 있음

## 마르코프 프로세스

- 다음 상태로 전이할 확률이 **현재 상태에만 의존**하는 확률 과정(마르코프한 과정)
  - $$s_t$$에서 $$s_{t+1}$$로 전이할 확률은 $$s_t$$하고만 관련이 있음, $$s_0, s_1, ..., s_{t-1}$$과는 관련이 없음
- 예)
  ![아이가 잠이 드는 마르코프 프로세스](/assets/img/2023-12-22-reinforcement-learning-2/MPBaby.png)
  - 시작 상태: $$s_0$$, 종료 상태: $$s_4$$
  - 1분마다 다음 상태로 **상태 전이(state transition)**
  - 각각의 상태는 다음 상태가 어디가 될지에 해당하는 확률이 있으며, 확률의 합은 100%
    - $$s_0$$에서는 40%의 확률로 $$s_1$$으로, 60%의 확률로 $$s_2$$로 전이
    - $$s_1$$에서는 90%의 확률로 $$s_1$$으로, 10%의 확률로 $$s_0$$로 전이
    - $$s_2$$에서는 70%의 확률로 $$s_3$$로, 30%의 확률로 $$s_4$$로 전이
    - $$s_3$$에서는 100%의 확률로 $$s_4$$로 전이
    - $$s_4$$에서는 종료(100%의 확률로 $$s_4$$로 전이)

> 종료 상태에서는 자신에게 전이할 확률이 100%라고 생각할 수 있음
{: .prompt-tip}

<br/>

$$
MP \equiv (S, P)
$$

- 상태의 집합 $$S$$
  - 가능한 상태들을 모두 모아놓은 집합
    - 예) $$S=\{s_0, s_1, s_2, s_3, s_4\}$$

- 전이 확률 행렬 $$P$$

### 전이 확률 행렬(transition probability matrix)

- 전이 확률 행렬 $$P$$
  - 전이 확률
  
  	$$
  	P_{ss^\prime}=\mathbb{P}[S_{t+1}=s^\prime\mid S_t=s]
  	$$

    - $$t$$에서의 상태가 $$s$$일 때, $$t+1$$에서의 상태가 $$s^\prime$$일 확률
    - 예) $$P_{s_0s_2}=0.6$$

  - 전이 확률을 행렬 형태로 표현할 수 있음
    - 예)

    $$
    P = \quad
    \begin{matrix}
     & \begin{matrix} s_0\; & s_1\; & s_2\; & s_3\; & s_4\; \end{matrix} \\
    \begin{matrix} s_0 \\ s_1 \\ s_2 \\ s_3 \\ s_4 \end{matrix}
    &
    \left[
    \begin{matrix}
    	    & 0.4 & 0.6 &     &     \\
    	0.1 & 0.9 &     &     &     \\
    	    &     &     & 0.7 & 0.3 \\
    	    &     &     &     & 1.0 \\
    	    &     &     &     & 1.0 \\
    \end{matrix}
    
    \right]
    \end{matrix}
    $$

    

    - $$s_0$$행, $$s_2$$열($$P_{s_0s_2}$$) = 0.6

# 2. 마르코프 리워드 프로세스(Markov Reward Process)

## 마르코프 리워드 프로세스

- 마르코프 프로세스에 **보상**의 개념이 추가
- 예)

  ![아이가 잠에 드는 MRP](/assets/img/2023-12-22-reinforcement-learning-2/MRPBaby.png)

  - 마르코프 프로세스 예시에서 보상이 추가된 형태

<br/>

$$
MRP \equiv (S, P, R, \gamma)
$$

- 상태의 집합 $$S$$
  - 마르코프 프로세스의 $$S$$와 같음
- 전이 확률 행렬 $$P$$
  - 마르코프 프로세스의 $$P$$와 같음
- 보상 함수 $$R$$

  $$
  R = \mathbb{E}[R_t\mid S_t=s]
  $$

  - 상태 $$s$$에 도착했을 때 받게 되는 **보상의 기댓값**
    - 기댓값인 이유는 특정 상태에 도달했을 때 받는 보상이 매번 달라질 수 있기 때문
    - 예) 동전을 던져 앞면이 나오면 500원을 갖고 뒷면이 나오면 갖지 못한다고 할 때, 보상은 바뀌지만 기댓값은 250원으로 설정할 수 있음

- 감쇠 인자 $$\gamma$$
  - 0과 1 사이의 수
  - 미래에 얻게 될 보상에 비해 **당장 얻게 될 보상을 얼마나 중요하게 여길지**를 나타내는 파라미터
    - 미래에 얻을 보상일수록 $$\gamma$$가 여러번 곱해져 작게 만듦


### 감쇠된 보상의 합, 리턴(return)

- MRP에서는 상태가 바뀔 때마다 보상을 받음
  - 상태 $$s_0$$에서 보상 $$R_0$$를 받고 시작하여 종료 상태 $$S_T$$에서 보상 $$R_T$$를 받고 끝남

  $$
  s_0,R_0,s_1,R_1,s_2,R_2,...,s_T,R_T
  $$

  - 이와 같은 하나의 여정을 **에피소드(episode)**라고 함
- 리턴 $$G_t$$

  $$
  G_t = R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \cdots
  $$

  - $$t$$부터 미래에 받을 **감쇠된 보상의 합**
  - 감쇠 인자 $$\gamma$$를 통해 미래에 얻게 될 보상에 가중치를 줄 수 있음
    - $$\gamma=0$$이면 미래의 보상을 모두 0이 되기 때문에 매우 그리디(greedy)하게 됨
    - $$\gamma=1$$이면 매우 장기적인 시야를 가지게 됨
  - 강화 학습은 **리턴이 최대가 되는 방향**으로 학습하는 것

### $$\gamma$$가 필요한 이유

- 수학적 편리성
  - $$\gamma$$를 1보다 작게 하여 $$G_t$$가 지나치게 큰 값을 갖는 것을 방지
- 여러가지 성향 설정 가능
  - 당장 눈앞의 보상을 더 선호하거나 매우 먼 미래의 보상을 더 선호하도록 설정 가능
- 미래에 대한 불확실성 반영
  - 미래에 대한 불확실성을 반영하기 위해 감쇠

## 에피소드 샘플링

- 시작 상태 $$s_0$$에서 출발하여 종료 상태 $$s_T$$에 도달할 때, $$s_1$$을 방문할 수도 있고, 방문하지 않을 수도 있음
  - 따라서 이에 따른 리턴도 달라짐
  - → 에피소드를 어떻게 **샘플링(sampling)** 하느냐에 따라 리턴이 달라짐
- **Monte-Carlo 접근법**: 샘플링을 통해 값을 유추하는 방법
- 예)
  - 에피소드 샘플링
    - 에피소드 1: 누움 → 일어남 → 누움 → 눈 감음 → 잠이 옴 → 잠듦
    - 에피소드 2: 누움 → 일어남 → 일어남 → 누움 → 눈 감음 → 잠이 옴 → 잠듦
    - 에피소드 3: 누움 → 눈 감음 → 잠이 옴 → 잠듦
  - 전이 확률 행렬 $$P$$를 이용해 무한히 샘플링 가능

## 상태 가치 함수(State Value Function)

$$
v(s) = \mathbb{E} [G_t\mid S_t=s]
$$

- 상태 $$s$$로부터 시작하여 얻는 **리턴의 기댓값**
- 가능한 에피소드가 무한하기 때문에 **샘플링을 통해 얻은 리턴의 평균으로 밸류를 근사 계산**
- 예)
  - 에피소드 1: 누움 → 일어남 → 누움 → 눈 감음 → 잠이 옴 → 잠듦
    - \$$-1 + 1 \times 0.9 - 1 \times 0.9^2 - 1 \times 0.9^3 + 0 \times 0.9^4 + 10 \times 0.9^5 \approx 4.3$$
  - 에피소드 2: 누움 → 일어남 → 일어남 → 누움 → 눈 감음 → 잠이 옴 → 잠듦
    - \$$-1 + 1 \times 0.9 + 1 \times 0.9^2 - 1 \times 0.9^3 - 1 \times 0.9^4 + 0 \times 0.9^5 + 10 \times 0.9^6 \approx 4.6$$
  - 에피소드 3: 누움 → 눈 감음 → 잠이 옴 → 잠듦
    - \$$-1 - 1 \times 0.9 + 0 \times 0.9^2 + 10 \times 0.9^3 \approx 5.4$$
  - \$$v(s_0) = \frac{4.3 + 4.6 + 5.4}{3} \approx 4.8$$

# 3. 마르코프 결정 프로세스(Markov Decision Process)

## 마르코프 결정 프로세스

$$
MDP \equiv (S, A, P, R, \gamma)
$$

- 상태의 집합 $$S$$
  - 마르코프 프로세스, 마르코프 보상 프로세스에서의 $$S$$와 같음
- 액션의 집합 $$A$$
  - 할 수 있는 행동의 집합
  - 에이전트는 액션의 집합 중 하나를 선택

- 전이 확률 행렬 $$P$$

  $$
  P_{ss^\prime}^a = \mathbb{P} [S_{t+1} = s^\prime \mid S_t=s, A_t=a]
  $$

  - $$t$$에서 상태가 $$s$$이고 액션 $$a$$를 했을 때, $$t+1$$에서 상태가 $$s^\prime$$가 될 확률
- 보상 함수 $$R$$

  $$
  R_s^a = \mathbb{E} [R_{t+1} \mid S_t=s, A_t=a]
  $$

  - $$t$$에서 상태가 $$s$$이고 액션 $$a$$를 했을 때, $$t+1$$에서 받을 보상의 기댓값
- 감쇠 인자 $$\gamma$$
  - MRP에서의 $$\gamma$$와 같음
- 예)

  ![아이 재우기 MDP](/assets/img/2023-12-22-reinforcement-learning-2/MDPBaby.png)

  - $$P_{s_2,s_0}^{a_1}=0.3$$, $$P_{s_2,s_1}^{a_1}=0.7$$

    > 확률 값이 적혀있지 않은 부분은 100%
    >
    > 예) $$P_{s_0,s_2}^{a_0}=1$$, $$P_{s_0,s_2}^{a_1}=0$$
    >
    {: .prompt-info}

  - MDP가 많이 복잡해지면 어떤 선택을 해야 할지 알기 어려워짐
    - **정책(policy)**: 각 상태에 따라 액션을 선택하는 규칙

## 정책 함수와 2가지 가치 함수

### 정책 함수(policy function)

- 각 상태에서 **어떤 액션을 선택**할지 정해주는 함수

$$
\pi(a\mid s)=\mathbb{P}[A_t=a\mid S_t=s]
$$

- 상태 $$s$$에서 액션 $$a$$를 선택할 확률
- 예)
  - $$\pi(a_{0}\mid s_{0})=0.2$$: $$s_0$$에서 $$a_0$$를 선택할 확률이 0.2라는 의미
  - $$\pi(a_1\mid s_0)=0.5$$: $$s_0$$에서 $$a_1$$을 선택할 확률이 0.5라는 의미
  - $$\pi(a_2\mid s_0)=0.3$$: $$s_0$$에서 $$a_2$$를 선택할 확률이 0.3라는 의미
  - 각 상태에서 할 수 있는 **모든 액션의 확률 값을 더하면 1**이 되어야 함

### 상태 가치 함수

$$
\begin{align}
v_\pi(s)
&=\mathbb{E}_\pi[r_{t+1}+\gamma r_{t+2}+\gamma^2 r_{t+2}+ \cdots\mid S_t=s]\\
&=\mathbb{E}_\pi[G_t\mid S_t=s] \\
\end{align}
$$

- $$s$$부터 끝까지 $$\pi$$를 따라서 움직일 때 얻는 리턴의 기댓값

### 액션 가치 함수(state-action value function)

$$
q_\pi(s,a)=\mathbb{E}_\pi[G_t\mid S_t=s,A_t=a]
$$

- $$s$$에서 $$a$$를 선택하고, 그 이후에는 $$\pi$$를 따라서 움직일 때 얻는 리턴의 기댓값

### $$v_\pi(s)$$ vs $$q_\pi(s, a)$$

- '**$$s$$에서 어떤 액션을 선택하는지**'에만 차이가 있음
- $$v_\pi(s)$$는 $$s$$에서 $$\pi$$가 액션을 선택
- $$q_\pi(s, a)$$는 $$s$$에서 $$a$$를 선택

# 4. Prediction과 Control

- **Prediction**: $$\pi$$가 주어졌을 때 각 상태의 밸류를 평가하는 문제
- **Control**: **최적 정책(optimal policy) $$\pi^*$$**를 찾는 문제
  - 최적 정책: 모든 $$\pi$$ 중 기대 리턴이 가장 큰 $$\pi$$
  - **최적 가치 함수(optimal value function) $$v^*$$**: $$\pi^*$$를 따를 때의 가치 함수

## 그리드 월드 예시

![그리드 월드](/assets/img/2023-12-22-reinforcement-learning-2/grid_world.png)

- **'출발'**에서 시작하여 **'종료'**에 도착하면 한 에피소드 종료
- 최단 경로를 통해 종료 상태에 도착하는 에피소드가 리턴이 가장 큼

### Prediction

- $$\pi$$가 주어졌을 때 각 상태의 밸류를 평가하는 문제
- 정책 $$\pi$$를 4방향 랜덤으로 가정
  - \$$\pi(동\mid s)=\pi(서\mid s)=\pi(남\mid s)=\pi(북\mid s)=0.25$$
- $$v_\pi(s_{11})$$를 구하는 것은 **매우 복잡**
  - 언뜻 보면 아래로 1칸 움직이면 끝나므로 간단해 보이지만, 4방향 랜덤이기 때문에 무한한 에피소드가 존재

### Control

- 최적 정책 $$\pi^*$$를 찾는 문제
- 항상 동쪽(오른쪽) 또는 남쪽(아래쪽)으로 이동하는 것이 $$\pi^*$$
- 하지만 일반적인 MDP에서 $$\pi^*$$를 찾는 것은 간단하지 않음