---
title: 이산수학 4. 집합
author: seyeon
date: 2024-04-02 01:00:00 +0900
categories: [Math, Discrete Mathematics]
tags: [discrete]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-04-02-discrete-mathematics-4/discrete_mathematics_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Philip Oroni
  
typora-root-url: ../
---

# 1. 집합의 개념

- 집합(set, $$A$$): 명확한 기준에 따라 공통 성질을 가지며 **<u>중복되지 않는 원소</u>**의 모임
  - 유한집합(finite set): 원소의 개수가 유한개인 집합
  - 무한집합(infinite set): 원소의 개수가 무한한 집합
- 집합의 표기방식
  - 원소 나열법: 원소를 일일이 나열
    - 예) $$A = \{1, 2, 3, 4, 5\}$$
  - 조건 제시법: 원소들의 공통 성질을 조건식으로 제시
    - 예) $$A=\{x \mid 0 \lt x \le 7, x \in \mathbb{R}\}$$
  - 벤 다이어그램: 포함 관계를 그림으로 보여주는 방법
- 기수(cardinality, $$\vert A \vert$$): 집합 $$A$$에 포함되는 원소의 개수
- 집합에 대한 원소의 포함관계
  - $$a \in A$$: $$a$$가 $$A$$의 원소이다.
  - $$a \notin A$$: $$a$$가 $$A$$의 원소가 아니다.

# 2. 집합의 종류

- 전체집합(universal set, $$U$$): 원소 전체를 포함하는 집합
- 공집합(empty set, $$\varnothing$$): 원소가 없는 집합, $$\vert\varnothing\vert=0$$
- 상등(equal, $$A = B$$​), 두 집합에 속하는 원소가 모두 동일
- 부분집합(subset, $$A \subseteq B$$): $$A$$의 모든 원소가 $$B$$​에 포함될 때
- 진부분집합(proper subset, $$A \subset B$$): $$A$$가 $$B$$의 부분집합이지만 상등이 아닐 때
- 집합 간의 포함관계
  - 모든 집합 $$A$$에 대하여, $$A \subseteq A$$
  - 모든 집합 $$A$$에 대하여, $$\varnothing \subseteq A$$
  - 모든 집합 $$A$$에 대하여, $$A \subseteq U$$
  - 집합 $$A$$, $$B$$, $$C$$에 대하여, $$A \subseteq B$$이고 $$B \subseteq C$$이면 $$A \subseteq C$$
  - 집합 $$A$$, $$B$$에 대하여, $$A=B \Leftrightarrow (A \subseteq B) \land (B \subseteq A)$$

# 3. 집합의 연산

- 합집합(union, $$A \cup B$$): $$A$$ 또는 $$B$$에 속하는 원소들로 이루어진 집합
- 교집합(intersection, $$A \cap B$$): $$A$$와 $$B$$ 모두에 속하는 원소들로 이루어진 집합
- 서로소(disjoint): 두 집합에 공통으로 포함되는 원소가 없는 경우
  - 교집합이 공집합, $$A \cap B = \varnothing$$​
- 여집합(complement set, $$\bar{A}$$ 또는 $$A^\prime$$): $$U$$에는 포함되지만 $$A$$는 포함되지 않는 원소들의 집합
- 차집합(difference, $$A - B$$): $$A$$는 포함되지만 $$B$$에는 포함되지 않는 원소들의 잡합
  - \$A \cap (A \cap B)^C$
- 대칭차집합(symmetric difference, $$A \oplus B$$): $$A$$에만 포함되거나 $$B$$에만 포함되는 원소들의 집합
  - \$(A - B) \cup (B - A)$
- 곱집합(product set, $$A \times B$$): $$a \in A$$, $$b \in B$$일 때, 순서상 $$(a, b)$$​의 집합
- 멱집합(power set, $$P(A)$$): 가능한 모든 부분집합을 원소로 갖는 집합, 공집합 포함
- 집합의 기수
  - 합집합: $$\vert A \cup B \vert = \vert A \vert + \vert B \vert - \vert A \cap B \vert$$​
    - 서로소인 경우, $$\vert A \cup B \vert = \vert A \vert + \vert B \vert$$​
    - 집합이 3개인 경우: $$\vert A \cup B \cup C \vert = \vert A \vert + \vert B \vert + \vert C \vert - \vert A \cap B \vert - \vert A \cap C \vert - \vert B \cap C \vert + \vert A \cap B \cap C \vert$$
  - 교집합: $$\vert A \cap B \vert = \vert A \vert + \vert B \vert - \vert A \cup B \vert$$
    - 집합이 3개인 경우: $$\vert A \cap B \cap C \vert = \vert A \vert + \vert B \vert + \vert C \vert - \vert A \cup B \vert - \vert A \cup C \vert - \vert B \cup C \vert + \vert A \cup B \cup C \vert$$​
  - 차집합: $$\vert A - B \vert = \vert A \vert - \vert A \cap B \vert$$
  - 대칭차집합: $$\vert A \oplus B \vert = \vert A \cup B \vert - \vert A \cap B \vert$$​
  - 곱집합: $$\vert A \times B \vert = \vert A \vert \times \vert B \vert$$
  - 멱집합: $$\vert P(A) \vert = 2^n$$

# 4. 집합의 대수법칙

## 항등법칙 (Identity Laws)
- 합집합의 항등법칙: $$ A \cup \varnothing = A $$
- 교집합의 항등법칙: $$ A \cap U = A $$

## 지배법칙 (Domination Laws)
- 합집합의 지배법칙: $$ A \cup U = U $$
- 교집합의 지배법칙: $$ A \cap \varnothing = \varnothing $$

## 멱등법칙 (Idempotent Laws)
- 합집합의 멱등법칙: $$ A \cup A = A $$
- 교집합의 멱등법칙: $$ A \cap A = A $$

## 교환법칙 (Commutative Laws)
- 합집합의 교환법칙: $$ A \cup B = B \cup A $$
- 교집합의 교환법칙: $$ A \cap B = B \cap A $$

## 결합법칙 (Associative Laws)
- 합집합의 결합법칙: $$ A \cup (B \cup C) = (A \cup B) \cup C $$
- 교집합의 결합법칙: $$ A \cap (B \cap C) = (A \cap B) \cap C $$

## 분배법칙 (Distributive Laws)
- 합집합에 대한 분배법칙: $$ A \cup (B \cap C) = (A \cup B) \cap (A \cup C) $$
- 교집합에 대한 분배법칙: $$ A \cap (B \cup C) = (A \cap B) \cup (A \cap C) $$

## 이중 보법칙 (Double Complement Laws)
- \$\bar{\bar{A}} = A$

## 보법칙 (Complement Laws)
- $$A \cup \bar{A} = U$$, $$\bar{\varnothing} = U$$
- $$A \cap \bar{A} = \varnothing$$, $$\bar{U} = \varnothing$$

## 드 모르간의 법칙 (De Morgan's Laws)
- 합집합에 대한 드 모르간의 법칙: $$ \overline{A \cup B} = \bar{A} \cap \bar{B} $$
- 교집합에 대한 드 모르간의 법칙: $$ \overline{A \cap B} = \bar{A} \cup \bar{B} $$

## 흡수법칙 (Absorption Laws)
- 합집합의 흡수법칙: $$ A \cup (A \cap B) = A $$
- 교집합의 흡수법칙: $$ A \cap (A \cup B) = A $$

# 5. 집합의 분할

- 분할(partition, $$A = \{A_1, A_2, \cdots, A_n\}$$): 공집합이 아닌 집합 $$A$$를 서로소이면서 공집합이 아닌 하나 이상의 부분집합으로 나누는 것
  - 분할의 조건
    - \$A_i \neq \varnothing$
    - $$i \neq j$$이면, $$A_i \cap A_j = \varnothing$$
    - \$A_i \subseteq A$
    - \$A = A_1 \cup A_2 \cup \cdots \cup A_n$

