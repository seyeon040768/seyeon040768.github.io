---
title: 확률 및 통계학 2. 대표값과 기술통계
author: seyeon
date: 2024-03-21 01:00:00 +0900
categories: [Math, Probability Statistics]
tags: [probability, statistics]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-03-21-probability-statistics-1/probability-statistics-main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의BoliviaInteligente
  
typora-root-url: ../
---

# 대표값

- 데이터를 대표할 수 있는 값
- 평균, 중앙값, 최빈값, 중앙범위 등이 있음

## 평균

$$
\text{average} = \frac{\text{sum}}{\text{count}}
$$

- 평균 = (데이터의 합) / (데이터의 개수)
- 모평균($$\mu$$): 모집단의 평균
- 표본평균($$\bar{x}$$): 표본의 평균
- 평균의 단점
  - 이상치(outlier)의 영향을 받음
  
    $$
    \begin{matrix}
    1 & 1 & 2 & 3 & 100
    \end{matrix}
    $$

    - 평균: $$\frac{1 + 1 + 2 + 3 + 100}{5}=21.4$$
    - 대부분 1, 2, 3이지만 이상치 100 때문에 평균이 커짐

## 중앙값

- 크기순으로 배열 했을 때 중간에 위치한 값
  - $$n$$이 홀수: $$\frac{n+1}{2}$$번째
  - $$n$$이 짝수: $$\frac{n}{2}$$번째와 $$\frac{n}{2}+1$$번째의 평균
- 이상치의 영향을 거의 받지 않음
- 예)

  $$
  \begin{matrix}
  1 & 1 & 2 & 3 & 100
  \end{matrix}
  $$

  - $$n=5$$이므로 $$\frac{5+1}{2}=3$$, 3번째 값인 2가 중앙값

## 최빈값

- 가장 빈도가 많은 값
- 질적 자료에 사용
- 최빈값이 2개일 경우 이봉자료라고 함
- 예)

  $$
  \begin{matrix}
  1 & 1 & 2 & 3 & 100
  \end{matrix}
  $$

  - 가장 많이 관측되는 값: 1


## 중앙범위

$$
\text{midrange}=\frac{\text{max} + \text{min}}{2}
$$

- 중앙범위 =최대값과 최소값의 평균
- 예)

  $$
  \begin{matrix}
  1 & 1 & 2 & 3 & 100
  \end{matrix}
  $$

  - 중앙값: $$\frac{1 + 100}{2} = 50.5$$

# 백분위수

- 위치점 $$p\%$$: 비율 $$p$$만큼이 그 값보다 작고 $$(1-p)$$만큼이 큰 값
- 백분위수 $$p_n$$: 위치점 $$n\%$$
- 예)

  $$
  \begin{array}{c|cccccccc}
  3 & 4 & 4 & 6 & 9\\
  4 & 3 & 6 & 7 & 8 & 9\\
  5 & 0 & 1 & 1 & 5 & 7 & 7 & 8 & 9\\
  6 & 0 & 0 & 4 & 4 & 7\\
  7 & 1 & 5 & 8 & 8 & 8 & 9\\
  8 & 4 & 6 & 8 & 8\\
  \end{array}
  $$

  - 백분위수 $$p_{25}$$
    - $$32개 \times 25\%=8$$, 8번째 수: 48
    - $$32개 \times 75\%=24$$, 24번째 수: 49
    - 따라서 $$p_{25} = \frac{48 + 49}{2} = 48.5$$
  - $$개수 \times p\%$$ 했을 때 정수면 $$(1-p)\%$$도 계산, 실수면 올림만 하면 됨

## 사분위수

- 제1사분위수($$Q_1$$): $$p_{25}$$
- 제2사분위수($$Q_2$$): $$\bar{x}$$, $$p_{50}$$
- 제3사분위수($$Q_3$$): $$p_{75}$$

## 십분위수

- 제1십분위수($$D_1$$), 제2십분위수($$D_2$$), ..., 제9십분위수($$D_9$$)
- $$D_1 = p_{10}$$, $$D_2 = p_{20}$$, ..., $$D_9 = p_{90}$$

# 산포도

- 자료들이 대표값 주위에서 어느 정도 분포되어 있는지를 나타내는 통계값

## 범위

$$
R = \max - \min
$$

- 범위 = 최댓값 - 최솟값

- 사분위수의 범위($$IQR$$)

  $$
  IQR = Q_3 - Q_1
  $$

## 분산

- 모집단 분산

  $$
  \sigma^2=\frac{\sum_{i+1}^{N}(x_i-\mu)^2}{N}
  $$

  - $$N$$: 모수의 개수
  - $$x_i-\mu$$: 편차
  - 간편식
  
    $$
    \sum_{i=1}^{k}f_i(x_i^\ast-\mu)^2=\sum_{i=1}^{k}f_ix_i^{\ast2}-N\mu^2
    $$

    - $$f_i$$: $$x_i$$의 빈도

- 표본 분산

  $$
  s^2=\frac{\sum_{i=1}^{n}(x_i-\bar{x})^2}{n-1}
  $$

  - 모분산과 비슷하게 하기 위해 $$n$$이 아닌 $$n-1$$로 나눔
  
- 도수분포표에서의 근사 분산

  $$
  \sigma^2=\frac{\sum_{i+1}^{N}f_i(x_i^\ast-\mu)^2}{N}
  $$

## 체비셰프 정리

- 분포 상관 없이, 적어도 $$(1-\frac{1}{k^2})\cdot 100\%$$의 자료가 $$\mu \pm k\sigma$$ 사이에 존재

- 예)

  - 전체의 $$90\%$$, $$\bar{x}=0.26$$, $$s=0.005$$

    $$
    \begin{align*}
    & 1-\frac{1}{k^2}=0.9\\
    & k=\sqrt{10} \simeq 3.16\\
    \end{align*}
    $$

    - $$0.26 \pm 3.16\times0.005$$ 범위에 $$90\%$$의 자료가 존재

  - 적어도 몇 $$\%$$가 0.20, 0.32 사이에 존재

    - 0.20과 0.32의 평균이 $$0.26 = \bar{x}$$이므로 둘 중 하나면 계산하면 됨

    $$
    \begin{align*}
    & 0.26 - k\times 0.005 = 0.20\\
    & k=12\\
    & 1-\frac{1}{k^2}\simeq0.99305\\
    \end{align*}
    $$

    - $$99.305\%$$ 사이에 존재
