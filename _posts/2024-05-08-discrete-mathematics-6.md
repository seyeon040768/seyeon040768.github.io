---
title: 이산수학 6. 관계
author: seyeon
date: 2024-05-08 01:00:00 +0900
categories: [Math, Discrete Mathematics]
tags: [discrete]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-05-08-discrete-mathematics-5/discrete_mathematics_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Philip Oroni
  
typora-root-url: ../
---

# 1. 관계의 개념

- 관계(relation, $$R$$: $$A \rightarrow B$$, $${}_{a}R_{b}$$) / 이항관계(binary relation): 집합 $$A$$, $$B$$가 있을 때, $$A$$에서 $$B$$로 가는 관계, $$A \times B$$의 부분집합
  - 예) $$\{(a_1, b_2), (a_2, b_5), (a_3, b_1)\}$$
- 정의역(domain, $$\text{dom}(R)$$): $$R$$에 속한 순서쌍의 첫 번째 원소가 포함된 집합, $$\text{dom}(R) = \{a \mid a \in A \}$$
- 공역(codomain, $$\text{codom}(R)$$): $$R$$에 속한 순서쌍의 두 번째 원소가 포함된 집합, $$\text{codom}(R) = \{ b \mid b \in B \}$$
- 치역(range, $$\text{ran}(R)$$): $$R$$에 속한 순서쌍의 두 번째 원소를 모아놓은 집합, 공역의 부분집합, $$\text{ran}(R) = \{b \mid (a, b) \in R \}$$
- $$n$$항 관계($$n$$-ary relation): $$n$$개의 집합 $$A_1, A_2, \cdots, A_n$$이 있을 때, $$A_1 \times A_2 \times \cdots \times A_n$$의 부분집합
- 역관계(inverse relation, $$R^{-1}$$): $$A$$에서 $$B$$로의 관계 $$R$$이 있을 때, $$B$$에서 $$A$$로의 관계, $$R^{-1} = \{(b, a) \in B \times A \mid (a, b) \in R \}$$

# 2. 관계의 표현

![arrow_diagram](/assets/img/2024-05-08-discrete-mathematics-6/arrow_diagram.png)

- 화살표 선도(arrow diagram): $$R$$을 화살표로 나타낸 도표

![coordinate_diagram](/assets/img/2024-05-08-discrete-mathematics-6/coordinate_diagram.png)

- 좌표 도표(coordinate diagram): $$R$$에서 $$A$$(정의역)의 원소를 $$x$$축에, $$B$$(공역)의 원소를 $$y$$축에 표시하여 좌표로 나타낸 도표
- 관계 행렬(relation matrix): $$R$$의 순서쌍을 행렬로 표기
  - $$A$$의 원소가 $$m$$개, $$B$$의 원소가 $$n$$개일 때, $$M_R$$은 $$m \times n$$ 행렬
  - 순서쌍에 속한 원소는 1로, 나머지는 0으로 표기

![directed_graph](/assets/img/2024-05-08-discrete-mathematics-6/directed_graph.png)

- 방향 그래프(directed graph): 하나의 집합 $$A$$에서 $$A$$로 가는 관계 $$R$$을 꼭짓점과 화살표를 이용하여 나타낸 그래프

# 3. 관계의 성질

- 반사 관계(reflexive relation): $$A$$에 대한 관계 $$R$$이 있을 때, 모든 $$a \in A$$에 대해 $$(a, a) \in R$$인 관계
  - 관계 행렬에서 대각선이 모두 1
- 비반사 관계(irreflexive relation): $$A$$에 대한 관계 $$R$$이 있을 때, 모은 $$a \in A$$에 대해 $$(a, a) \notin R$$인 관계
  - 관계 행렬에서 대각선이 모두 0
- 대칭 관계(symmetric relation): 어떤 $$a, b \in A$$에 대해 $$(a, b) \in R$$이면 $$(b, a) \in R$$인 관계
- 반대칭 관계(antisymmetric relation): 어떤 $$a, b \in A$$에 대해 $$(a, b) \in R$$이고 $$(b, a) \in R$$이면 $$a = b$$인 관계
- 추이 관계(transitive relation): 어떤 $$a, b, c \in A$$에 대해 $$(a, b) \in R$$이고, $$(b, c) \in R$$이면 $$(a, c) \in R$$인 관계

# 4. 합성 관계

- 합성 관계(composite relation, $$S \circ R$$): $$A$$에서 $$B$$로의 관계 $$R$$과 $$B$$에서 $$C$$로의 관계 $$S$$가 있을 때, 이 두 관계를 이용해 구하는 $$A$$에서 $$C$$로의 관계
- 합성 관계의 거듭제곱 정리 예정
