---
title: 강화학습 Chapter 1. 강화 학습이란
author: seyeon
date: 2023-12-21 20:00:00 +0900
categories: [AI, Reinforcement Learning]
tags: [AI, RL]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2023-12-21-reinforcement-learning-1/reinforcement_learning_main.png
  alt: Reinforcement Learning Diagram
typora-root-url: ../
---

# 참고 자료

이 글은 [노승은, [바닥부터 배우는 강화 학습](https://shop.youngjin.com/goods/view?no=103), 영진닷컴(2022)]을 바탕으로 작성되었습니다.

# 1. 기계 학습(machine learning)의 분류

- 지도 학습(supervised learning)
  - **정답이 있는** 데이터를 통해 학습
  - 회귀, 분류 등이 해당
- 비지도 학습(unsupervised learning)
  - **정답이 없는** 데이터를 통해 학습
  - 군집화, 생성 알고리즘 등이 해당
- 강화 학습(reinforcement learning)
  - 보상을 최대화 하기 위해 **시행착오**를 거쳐 학습

# 2. 순차적 의사결정 문제(sequential decision making)

- 강화 학습이 해결하고자 하는 문제
- 각 단계의 **결정이 다음 단계에 영향**을 주는 문제
- 예)
  - 샤워
    - 옷을 벗는다 → 샤워를 한다 → 물기를 닦는다 → 옷을 입는다
    - 만약 순서가 바뀐다면(옷을 벗는다 → 옷을 입는다 → 물기를 닦는다 → 샤워를 한다) 이상한 결과가 나올 수도 있음
  - 게임
    - 기본 공격, 스킬, 이동 등 여러 행동을 할 수 있으며 미래에 영향을 끼침

# 3. 보상(reward)

- 의사결정을 **얼마나 잘하고 있는지** 알려주는 신호
- 강화 학습의 목적이 보상의 총합, 즉 **누적 보상(cumulative reward)**를 **최대화**하는 것

## 보상의 3가지 특징

### 어떻게 X, 얼마나 O

- **얼마나** 잘하고 있는지 알려줌
- **어떻게** 해야 높은 보상을 얻을 수 있는지 알려주지 않음

### 스칼라

- **벡터**가 아닌 **스칼라** 형태
- 여러 목표에 대한 보상을 하나의 스칼라 값으로 표현
  - 가중치를 이용

### 희소하고 지연된 보상

- 행동과 보상이 일대일 대응되지 않음
- 행동에 대한 보상이 한참 뒤에 주어질 수 있기 때문에 어떤 행동에 따른 보상인지 알기 어려움

# 4. 에이전트(agent)와 환경(environment)

![reinforcement_learning_diagram](/assets/img/2023-12-21-reinforcement-learning-1/reinforcement_learning_main.png)

- 에이전트
  - 강화 학습의 **주체**(학습하는 대상)
  - 액션($$a_t$$)
    - 에이전트가 하는 행동
    - **액션**을 통해 **상태**을 변화시킴
- 환경
  - 에이전트를 제외한 모든 요소
  - 상태($$s_t$$)
    - **환경**에 대한 모든 정보를 수로 표현
    - **액션**에 의해 변화
  - 보상($$r_t$$)
    - 에이전트에게 줄 보상
- 루프
  - **틱(tick)** 또는 **타임 스텝(time step)**
    - 에이전트와 환경이 한번 상호작용 했을 때, 1틱이 지났다고 표현
    - 이산적(discrete)
  - 에이전트의 루프
    1. 현재 상황 $$s_t$$에서 어떤 액션을 할지 $$a_t$$ 결정
    2. 결정된 $$a_t$$를 환경으로 보냄
    3. 환경으로부터 그에 따른 보상 $$r_{t+1}$$과 다음 상태 $$s_{t+1}$$를 받음
  - 환경의 루프
    1. 에이전트로부터 받은 액션 $$a_t$$를 통해 상태 변화 $s_t \rarr s_{t+1}$를 일으킴
    2. 에이전트에게 줄 보상 $$r_{t+1}$$ 계산
    3. $$s_{t+1}$$과 $$r_{t+1}$$을 에이전트에게 전달

# 5. 강화 학습의 위력

- 병렬성
  - 수많은 시뮬레이터를 통해 **동시에 학습** 가능
- 자가 학습(self-learning)의 매력
  - 혼자 스스로 학습하기 때문에 **무한한 가능성**을 지님