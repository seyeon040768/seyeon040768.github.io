---
title: 이산수학 3. 증명
author: seyeon
date: 2024-03-26 01:00:00 +0900
categories: [Math, Discrete Mathematics]
tags: [discrete]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-03-26-discrete-mathematics-3/discrete_mathematics_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Philip Oroni
  
typora-root-url: ../
---

# 1. 증명의 이해

- 증명(proof): 하나의 명제가 참($$T$$)임을 확인하는 과정
- 공리(axiom): 별도의 증명 없이도 항상 참($$T$$)이라고 판단되는 명제
  - 예) 1은 자연수
- 정의(definition): 개념이나 기호의 의미를 확실하게 규정한 문장
- 정리(theorem): 공리와 정의를 통해 참($$T$$)으로 확인된 명제

# 2. 직접 증명법

- 직접 증명법(direct proof): $$p \rightarrow q$$가 참($$T$$)임을 증명하기 위해 전제 $$p$$를 참($$T$$)으로 가정햇을 때, 결론 $$q$$도 참($$T$$)임을 증명하는 방법
- 예)
  - 두 짝수 $$m$$과 $$n$$의 합이 짝수임을 증명
    - $$p \rightarrow q$$: 두 정수 $$m$$과 $$n$$이 짝수이면, $$m$$과 $$n$$의 합은 짝수이다.
    - $$p$$: 두 정수 $$m$$과 $$n$$이 짝수이다.
    - $$q$$: $$m$$과 $$n$$의 합은 짝수이다.
    - 증명
      - $$m = 2k \; (k \in \mathbf{Z})$$, $$n = 2l \; (l \in \mathbf{Z})$$​
      - \$m + n = 2k + 2l = 2(k + l) = 2a \; (a \in \mathbf{Z})$
  - 모든 정수 $$x$$에 대하여, $$x^2-x$$는 짝수임을 증명
    - $$p$$: 정수 $$x$$는 짝수이다.
    - $$q$$: 정수 $$x$$는 홀수이다.
    - $$r$$: $$x^2-x$$​는 짝수이다.
    - $$(p \land q) \rightarrow r$$: 모든 정수 $$x$$에 대하여, $$x^2-x$$는 짝수이다.
    - 증명
      - \$(p \land q) \rightarrow r \equiv (p \rightarrow r) \land (q \rightarrow r)$
      - $$p \rightarrow r$$: $$x^2-x = (2k)^2-2k=2(2k^2-k)=2a$$
      - $$q \rightarrow r$$: $$x^2-x=(2k-1)^2-(2k-1)=2(2k-1)(k-1)=2(2k^2-3k+1)=2a$$

# 3. 간접 증명법

## 모순 증명법(proof by contradiction)

$$
\begin{align*}
p \rightarrow q
& \equiv \neg p \lor q\\
& \equiv \neg p \lor \neg(\neg q)\\
& \equiv \neg(p \land \neg q)

\end {align*}
$$

- 조건 명제 $$p \rightarrow q$$와 $$\neg (p \land \neg q)$$가 동치임을 이용해 $$p \land \neg q$$가 거짓($$F$$​)임을 보이는 방법
  - $$p \land \neg q = F$$면 $$p = T$$이고, $$q = F$$
- 예)
  - 두 짝수 $$m$$과 $$n$$의 합이 짝수임을 증명
    - $$p \rightarrow q$$: 두 정수 $$m$$과 $$n$$이 짝수이면, $$m$$과 $$n$$의 합은 짝수이다.
    - $$p$$: 두 정수 $$m$$과 $$n$$이 짝수이다.
    - $$q$$: $$m$$​과 $$n$$​의 합은 짝수이다.
    - $$\neg q$$: $$m$$과 $$n$$의 합은 짝수가 아니다.(홀수이다.)
    - $$p \land \neg q$$: 두 정수 $$m$$과 $$n$$이 짝수이고, $$m$$과 $$n$$의 합은 짝수가 아니다.
    - 증명
      - $$m = 2k \; (k \in \mathbf{Z})$$, $$n = 2l \; (l \in \mathbf{Z})$$​
      - \$m + n = 2k + 2l = 2(k + l) = 2a \; (a \in \mathbf{Z})$
      - 짝수이므로 $$p \land \neg q$$는 거짓, 따라서 $$p \rightarrow q$$는 참

## 대우 증명법(proof by contrapositive)

- 조건 명제 $$p \rightarrow q$$와 이에 대한 대우 명제 $$\neg q \rightarrow \neg p$$가 동치임을 이용하여 증명하는 방법
- 예)
  - $$5m+4$$가 $$4$$로 나누어 떨어지지 않으면, 정수 $$m$$도 $$4$$로 나누어 떨어지지 않음을 증명
    - $$p \rightarrow q$$: $$5m+4$$가 $$4$$로 나누어 떨어지지 않으면, 정수 $$m$$도 $$4$$로 나누어 떨어지지 않는다.
    - $$p$$: $$5m+4$$가 $$4$$로 나누어 떨어지지 않는다.
    - $$q$$: 정수 $$m$$은 $$4$$로 나누어 떨어지지 않는다.
    - $$\neg p$$: $$5m+4$$가 $$4$$로 나누어 떨어진다.
    - $$\neg q$$: 정수 $$m$$이 $$4$$로 나누어 떨어진다.
    - $$\neg q \rightarrow \neg p$$: 정수 $$m$$이 $$4$$로 나누어 떨어지면, $$5m+4$$는 $$4$$로 나누어 떨어진다.
    - 증명
      - $$m=4k$$, $$k$$는 정수
      - $$5m+4 = 20k + 4 = 4(5k + 1) = 4a$$
      - $$a$$는 정수이므로 $$5m+4$$는 $$4$$의 배수

 ## 존재 증명법(existence proof)

- 명제가 참($$T$$)이 되는 예를 찾아서 증명하는 방법
- 예)
  - 어떤 소수 $$n$$에 대하여, $$n + 4$$도 소수인지 증명
    - $$3 + 4 = 7$$, 3과 7 모두 소수

## 반례 증명법(proof by counter-example)

- 명제가 모순이 되는 예를 찾아서 증명하는 방법
- 예)
  - 모든 소수 $$n$$에 대하여, $$n + 4$$도 소수인지 증명
    - $$5 + 4 = 9$$, 5는 소수이지만 9는 소수가 아님

# 4. 수학적 귀납법(mathematical induction)

- 0보다 크거나 같은 정수 범위에서 발생하는 일정한 규칙을 나타내는 명제 $$P(n)$$이 성립함을 증명하는 방법

- 수학적 귀납법의 절차

  1. 기본 가정: 명제의 논의영역 $$D$$의 첫 번째 값 $$d$$에 대하여, $$P(d)$$가 참($$T$$)임을 보인다.
  2. 귀납 가정: 논의영역에 속하는 임의의 값 $$k$$에 대하여, $$P(k)$$가 참($$T$$)이라고 가정한다.
  3. 귀납 증명: 기본 가정과 귀잡 가정을 이용해 논의영역에 속하는 값 $$k+1$$에 대하여, $$P(k+1)$$이 참($$T$$)임을 증명한다.

- 예)

  - $$n \ge 1$$인 자연수 $$n$$에 대하여 $$1 + 2 + \cdots + n = \frac{n(n+1)}{2}$$임을 증명

    - 논의영역 $$D = \{ n \mid n \ge 1, n \in N \}$$

    - 명제 $$P(n) = 1 + 2 + \cdots + n = \frac{n(n+1)}{2}$$

    - 기본 가정: $$P(1) = \frac{1 \times 2}{2}=1$$, 참($$T$$)

    - 귀납 가정: $$P(k)=1 + 2 + \cdots + k = \frac{k(k+1)}{2}$$이 참($$T$$)이라고 가정

    - 귀납 증명
      $$
      \begin{align*}
      P(k+1)
      & = P(k) + k + 1\\
      & = \frac{k(k+1)}{2} + k + 1\\
      & = \frac{k^2 + 3k + 2}{2}\\
      & = \frac{(k+1)(k+2)}{2}\\
      & = \frac{(k+1)((k+1)+1)}{2}\\
      \end{align*}
      $$

    - 따라서 $$P(k+1)$$은 참($$T$$)

    - 따라서 명제 $$P(n)$$는 참($$T$$)

