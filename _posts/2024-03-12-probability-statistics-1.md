---
title: 확률 및 통계학 1. 모집단과 표본
author: seyeon
date: 2024-03-12 01:00:00 +0900
categories: [Math, Probability Statistics]
tags: [probability, statistics]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-03-12-probability-statistics-1/probability-statistics-main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 BoliviaInteligente
  
typora-root-url: ../
---

# 모집단과 표본

- 모집단: 연구하고 싶은 집단 전체
  - 실제로 모집단에 대해 통계를 내는 것은 매우 어려움
    - 수가 너무 많기 때문
  - 모수: 모집단에서 수집한 정보
    - 모평균($$\mu$$): 모수의 평균
    - 모분산($$\sigma^\prime$$): 모수의 분산
    - 모표준편차($$\sigma$$): 모수의 표준편차
- 포본: 모집단의 일부
  - 모집단의 일부를 관찰하여 통계를 산출
    - 표본을 바탕으로 모집단을 통계적 추론
  - 통계량: 표본에서 수집한 정보
    - 표본평균($$\bar{x}$$): 표본의 평균
    - 표본분산($$s^\prime$$): 표본의 분산
    - 표본표준편차($$s$$): 표본의 표준편차

# 자료의 종류와 척도

## 자료의 종류

- 양적 자료: 수치가 의미 있는 데이터
  - 연속 자료: 수치가 연속적인 데이터
    - 예) 키, 몸무게
  - 이산 자료: 수치가 이산적인 데이터
    - 예) 주사위, 사건의 발생 건수
- 질적 자료: 수치가 의미 없는 데이터
  - 예) 남자: 1, 여자: 2

## 자료의 척도

- 명목 척도: 범주로 구분
  - 사칙연산 불가
  - 빈도 분석
  - 예) 성별
- 순위 척도: 명목 척도 + 순위
  - 예) 등수
- 구간 척도: 절대 영점이 없음
  - 사칙연산 불가
  - 예) IQ
    - IQ80보다 IQ160이 2배 더 똑똑한 것은 아님
- 비율 척도: 절대 영점 존재
  - 사칙연산 가능
  - 예) 키, 몸무게

# 자료 시각화

## 도수분표포

- 계급과 도수로 나타낸 표
  - 계급: 자료의 범위
  - 도수: 계급에 속하는 자료의 수
- 도수분표포 작성 방법
  1. 자료의 범위: $$R = max - min$$
  2. 계급의 수: $$c=\text{round}(3.3(\log_{10}n) + 1)$$​
     - 이 계산법은 추천일 뿐
     - 주로 5개에서 15개 이내로 설정
  3. 계급 구간 설정: $$w=\frac{R}{c}$$​
     - 계급 구간은 주로 5의 배수 또는 2로 설정
     - $$min$$과 $$max$$가 계급의 경계에 겹치지 않도록 설정
     - 급간격: i번째 급상한 - (i-1)번째 급하한
  4. 계급값: $$\frac{하한 + 상한}{2}$$​
     - 계급의 중간값
  5. 도수 계산: $$f$$
     - 상대 도수: $$\frac{f}{n}$$
     - 누적 도수: 위에서부터 누적된 도수

- 예)

  - 자료
  
    $$
    \begin{matrix}
    71 & 64 & 70 & 78 & 58 & 49 & 79 & 65 & 83 & 69\\
    62 & 47 & 60 & 70 & 66 & 79 & 63 & 60 & 67 & 92\\
    59 & 67 & 66 & 78 & 63 & 62 & 69 & 56 & 66 & 81\\
    68 & 86 & 70 & 66 & 82 & 72 & 73 & 54 & 70 & 71
    \end{matrix}
    $$
    
  - 작성
  
    1. $$min = 47$$, $$max=92$$, $$R=92-47=45$$
    2. \$c=\text{round}(3.3(\log_{10}40) + 1)=6$
    3. $$w=\frac{45}{6}=7.5$$, 5의 배수로 설정: $$7.5 \rightarrow 10$$
  
    |      계급       | 도수 | 계급값 | 상대 도수 | 누적 도수 |
    | :-------------: | :--: | :----: | :-------: | :-------: |
    |  $$40\sim 50$$  |  2   |   45   |   0.05    |     2     |
    | $$50 \sim 60$$  |  4   |   55   |    0.1    |     6     |
    | $$60 \sim 70$$  |  17  |   65   |   0.425   |    23     |
    | $$70 \sim 80$$  |  12  |   75   |    0.3    |    35     |
    | $$80 \sim 90$$  |  4   |   85   |    0.1    |    39     |
    | $$90 \sim 100$$ |  1   |   95   |   0.025   |    40     |
    |      total      |  40  |        |     1     |           |

## 그래프

- 막대그래프: 도수, 상대 도수에 따른 막대를 이용
  - 빈도 분석

- 원그래프: 도수, 상대 도수가 차지하는 비율로 원을 나눔
  - 비율 분석

- 히스토그램: 도수분포표에서의 막대그래프
  - 폭 일정
  - 연속형 데이터에 사용
    - 일반 막대그래프로 연속형 데이터를 그리면 값이 너무 많아 복잡하기 때문

- 줄기-잎: 높은 자리와 낮은 자리로 분할 후 표로 표현
  - 정보를 잃지 않고 분포를 쉽게 파악
  - 자료
  
    $$
    \begin{matrix}
    64 & 84 & 82 & 81 & 68 & 85 & 76 & 89 & 93\\
    77 & 66 & 64 & 86 & 74 & 64 & 70 & 53 \\
    98 & 59 & 79 & 57 & 59 & 65 & 67 & 80
    \end{matrix}
    $$
    
  - 작성
  
    $$
    \begin{array}{c|cccccc}
    5 & 3 & 7 & 9 & 9\\
    6 & 4 & 4 & 4 & 5 & 6 & 7 & 8\\
    7 & 0 & 4 & 6 & 7 & 9\\
    8 & 0 & 1 & 2 & 4 & 5 & 6 & 9\\
    9 & 3 & 8
    \end{array}
    $$