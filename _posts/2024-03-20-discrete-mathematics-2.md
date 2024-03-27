---
title: 이산수학 2. 명제와 논리
author: seyeon
date: 2024-03-20 01:00:00 +0900
categories: [Math, Discrete Mathematics]
tags: [discrete]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-03-20-discrete-mathematics-2/discrete_mathematics_main.jpg
  lqip: data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEASABIAAD/4gxYSUNDX1BST0ZJTEUAAQEAAAxITGlubwIQAABtbnRyUkdCIFhZWiAHzgACAAkABgAxAABhY3NwTVNGVAAAAABJRUMgc1JHQgAAAAAAAAAAAAAAAAAA9tYAAQAAAADTLUhQICAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABFjcHJ0AAABUAAAADNkZXNjAAABhAAAAGx3dHB0AAAB8AAAABRia3B0AAACBAAAABRyWFlaAAACGAAAABRnWFlaAAACLAAAABRiWFlaAAACQAAAABRkbW5kAAACVAAAAHBkbWRkAAACxAAAAIh2dWVkAAADTAAAAIZ2aWV3AAAD1AAAACRsdW1pAAAD+AAAABRtZWFzAAAEDAAAACR0ZWNoAAAEMAAAAAxyVFJDAAAEPAAACAxnVFJDAAAEPAAACAxiVFJDAAAEPAAACAx0ZXh0AAAAAENvcHlyaWdodCAoYykgMTk5OCBIZXdsZXR0LVBhY2thcmQgQ29tcGFueQAAZGVzYwAAAAAAAAASc1JHQiBJRUM2MTk2Ni0yLjEAAAAAAAAAAAAAABJzUkdCIElFQzYxOTY2LTIuMQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAWFlaIAAAAAAAAPNRAAEAAAABFsxYWVogAAAAAAAAAAAAAAAAAAAAAFhZWiAAAAAAAABvogAAOPUAAAOQWFlaIAAAAAAAAGKZAAC3hQAAGNpYWVogAAAAAAAAJKAAAA+EAAC2z2Rlc2MAAAAAAAAAFklFQyBodHRwOi8vd3d3LmllYy5jaAAAAAAAAAAAAAAAFklFQyBodHRwOi8vd3d3LmllYy5jaAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABkZXNjAAAAAAAAAC5JRUMgNjE5NjYtMi4xIERlZmF1bHQgUkdCIGNvbG91ciBzcGFjZSAtIHNSR0IAAAAAAAAAAAAAAC5JRUMgNjE5NjYtMi4xIERlZmF1bHQgUkdCIGNvbG91ciBzcGFjZSAtIHNSR0IAAAAAAAAAAAAAAAAAAAAAAAAAAAAAZGVzYwAAAAAAAAAsUmVmZXJlbmNlIFZpZXdpbmcgQ29uZGl0aW9uIGluIElFQzYxOTY2LTIuMQAAAAAAAAAAAAAALFJlZmVyZW5jZSBWaWV3aW5nIENvbmRpdGlvbiBpbiBJRUM2MTk2Ni0yLjEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAHZpZXcAAAAAABOk/gAUXy4AEM8UAAPtzAAEEwsAA1yeAAAAAVhZWiAAAAAAAEwJVgBQAAAAVx/nbWVhcwAAAAAAAAABAAAAAAAAAAAAAAAAAAAAAAAAAo8AAAACc2lnIAAAAABDUlQgY3VydgAAAAAAAAQAAAAABQAKAA8AFAAZAB4AIwAoAC0AMgA3ADsAQABFAEoATwBUAFkAXgBjAGgAbQByAHcAfACBAIYAiwCQAJUAmgCfAKQAqQCuALIAtwC8AMEAxgDLANAA1QDbAOAA5QDrAPAA9gD7AQEBBwENARMBGQEfASUBKwEyATgBPgFFAUwBUgFZAWABZwFuAXUBfAGDAYsBkgGaAaEBqQGxAbkBwQHJAdEB2QHhAekB8gH6AgMCDAIUAh0CJgIvAjgCQQJLAlQCXQJnAnECegKEAo4CmAKiAqwCtgLBAssC1QLgAusC9QMAAwsDFgMhAy0DOANDA08DWgNmA3IDfgOKA5YDogOuA7oDxwPTA+AD7AP5BAYEEwQgBC0EOwRIBFUEYwRxBH4EjASaBKgEtgTEBNME4QTwBP4FDQUcBSsFOgVJBVgFZwV3BYYFlgWmBbUFxQXVBeUF9gYGBhYGJwY3BkgGWQZqBnsGjAadBq8GwAbRBuMG9QcHBxkHKwc9B08HYQd0B4YHmQesB78H0gflB/gICwgfCDIIRghaCG4IggiWCKoIvgjSCOcI+wkQCSUJOglPCWQJeQmPCaQJugnPCeUJ+woRCicKPQpUCmoKgQqYCq4KxQrcCvMLCwsiCzkLUQtpC4ALmAuwC8gL4Qv5DBIMKgxDDFwMdQyODKcMwAzZDPMNDQ0mDUANWg10DY4NqQ3DDd4N+A4TDi4OSQ5kDn8Omw62DtIO7g8JDyUPQQ9eD3oPlg+zD88P7BAJECYQQxBhEH4QmxC5ENcQ9RETETERTxFtEYwRqhHJEegSBxImEkUSZBKEEqMSwxLjEwMTIxNDE2MTgxOkE8UT5RQGFCcUSRRqFIsUrRTOFPAVEhU0FVYVeBWbFb0V4BYDFiYWSRZsFo8WshbWFvoXHRdBF2UXiReuF9IX9xgbGEAYZRiKGK8Y1Rj6GSAZRRlrGZEZtxndGgQaKhpRGncanhrFGuwbFBs7G2MbihuyG9ocAhwqHFIcexyjHMwc9R0eHUcdcB2ZHcMd7B4WHkAeah6UHr4e6R8THz4faR+UH78f6iAVIEEgbCCYIMQg8CEcIUghdSGhIc4h+yInIlUigiKvIt0jCiM4I2YjlCPCI/AkHyRNJHwkqyTaJQklOCVoJZclxyX3JicmVyaHJrcm6CcYJ0kneierJ9woDSg/KHEooijUKQYpOClrKZ0p0CoCKjUqaCqbKs8rAis2K2krnSvRLAUsOSxuLKIs1y0MLUEtdi2rLeEuFi5MLoIuty7uLyQvWi+RL8cv/jA1MGwwpDDbMRIxSjGCMbox8jIqMmMymzLUMw0zRjN/M7gz8TQrNGU0njTYNRM1TTWHNcI1/TY3NnI2rjbpNyQ3YDecN9c4FDhQOIw4yDkFOUI5fzm8Ofk6Njp0OrI67zstO2s7qjvoPCc8ZTykPOM9Ij1hPaE94D4gPmA+oD7gPyE/YT+iP+JAI0BkQKZA50EpQWpBrEHuQjBCckK1QvdDOkN9Q8BEA0RHRIpEzkUSRVVFmkXeRiJGZ0arRvBHNUd7R8BIBUhLSJFI10kdSWNJqUnwSjdKfUrESwxLU0uaS+JMKkxyTLpNAk1KTZNN3E4lTm5Ot08AT0lPk0/dUCdQcVC7UQZRUFGbUeZSMVJ8UsdTE1NfU6pT9lRCVI9U21UoVXVVwlYPVlxWqVb3V0RXklfgWC9YfVjLWRpZaVm4WgdaVlqmWvVbRVuVW+VcNVyGXNZdJ114XcleGl5sXr1fD19hX7NgBWBXYKpg/GFPYaJh9WJJYpxi8GNDY5dj62RAZJRk6WU9ZZJl52Y9ZpJm6Gc9Z5Nn6Wg/aJZo7GlDaZpp8WpIap9q92tPa6dr/2xXbK9tCG1gbbluEm5rbsRvHm94b9FwK3CGcOBxOnGVcfByS3KmcwFzXXO4dBR0cHTMdSh1hXXhdj52m3b4d1Z3s3gReG54zHkqeYl553pGeqV7BHtje8J8IXyBfOF9QX2hfgF+Yn7CfyN/hH/lgEeAqIEKgWuBzYIwgpKC9INXg7qEHYSAhOOFR4Wrhg6GcobXhzuHn4gEiGmIzokziZmJ/opkisqLMIuWi/yMY4zKjTGNmI3/jmaOzo82j56QBpBukNaRP5GokhGSepLjk02TtpQglIqU9JVflcmWNJaflwqXdZfgmEyYuJkkmZCZ/JpomtWbQpuvnByciZz3nWSd0p5Anq6fHZ+Ln/qgaaDYoUehtqImopajBqN2o+akVqTHpTilqaYapoum/adup+CoUqjEqTepqaocqo+rAqt1q+msXKzQrUStuK4trqGvFq+LsACwdbDqsWCx1rJLssKzOLOutCW0nLUTtYq2AbZ5tvC3aLfguFm40blKucK6O7q1uy67p7whvJu9Fb2Pvgq+hL7/v3q/9cBwwOzBZ8Hjwl/C28NYw9TEUcTOxUvFyMZGxsPHQce/yD3IvMk6ybnKOMq3yzbLtsw1zLXNNc21zjbOts83z7jQOdC60TzRvtI/0sHTRNPG1EnUy9VO1dHWVdbY11zX4Nhk2OjZbNnx2nba+9uA3AXcit0Q3ZbeHN6i3ynfr+A24L3hROHM4lPi2+Nj4+vkc+T85YTmDeaW5x/nqegy6LzpRunQ6lvq5etw6/vshu0R7ZzuKO6070DvzPBY8OXxcvH/8ozzGfOn9DT0wvVQ9d72bfb794r4Gfio+Tj5x/pX+uf7d/wH/Jj9Kf26/kv+3P9t////2wBDAAQCAwMDAgQDAwMEBAQEBQkGBQUFBQsICAYJDQsNDQ0LDAwOEBQRDg8TDwwMEhgSExUWFxcXDhEZGxkWGhQWFxb/2wBDAQQEBAUFBQoGBgoWDwwPFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhb/wAARCAAKAA8DASIAAhEBAxEB/8QAFgABAQEAAAAAAAAAAAAAAAAABgMH/8QAJRAAAgECBQQDAQAAAAAAAAAAAQIDBAUABhESMSEiQVEHEzJC/8QAFQEBAQAAAAAAAAAAAAAAAAAABgf/xAAcEQACAgIDAAAAAAAAAAAAAAABAwARBBMhIlH/2gAMAwEAAhEDEQA/AJ3qpzpkO5yihpTU5fjcyxmIBlC87COVY/n13A+8KMvfI9ruVtM00J3qvaafVvsJbaoC9ddwjlcafyAfOE0yq4ZHAZW7WBGoIPIOMOtzNRx3SajY08kNMzxPEdhjY1mwlSOCUVV6eABwMEl9rBlUzGbVhpFEecXP/9k=
  alt: Unsplash의 Philip Oroni
  
typora-root-url: ../
---

# 1. 명제

- 진리값(truth value)
  - 참(true, $$T$$)이나 거짓(false, $$F$$)를 가리키는 값
- 명제(proposition)
  - 객관적인 기준으로 진리값을 구분할 수 있는 문장
  - $$p$$, $$q$$, $$r$$처럼 소문자로 표현
  - 예)
    - $$10 \gt 5$$: 참인 명제
    - $$5+2=8$$: 거짓인 명제
    - $$x \gt 1$$: $$x$$가 뭔지 알 수 없으므로 명제가 아님

# 2. 논리 연산자

- 합성 명제(compound proposition)
  - 하나 이상의 명제들이 논리 연산자에 의해 결합된 명제
  - 예)
    - \$\neg p$
    - \$p \land q$

- 진리표(truth table)
  - 합성 명제를 구성하는 명제의 진리값에 따른 논리 연산 결과를 나타낸 표
  - 예)
  
    $$
    \begin{array}{|c c|c|}
    p & q & p\land q\\
    \hline
    T & T & T\\
    T & F & F\\
    F & T & F\\
    F & F & F\\
    \end{array}
    $$

## 부정

- 부정(not): $$\neg p$$ 또는 $$\sim p$$​
  - 단항 연산자
  - $$p$$의 부정: $$p$$가 아니다
  - 진리표

    $$
    \begin{array}{|c|c|}
    p & \neg p\\
    \hline
    T & F\\
    F & T
    \end{array}
    $$

  - 예)
    - $$p$$: 뉴욕은 미국의 동부에 있다., $$\neg p$$: 뉴욕은 미국의 동부에 있지 않다.
    - $$p$$: $$3+4=5$$, $$\neg p$$: $$3 + 4 \neq 5$$

## 논리곱

- 논리곱(and): $$p \land q$$
  - 이항 연산자
  - $$p$$ 그리고 $$q$$
  - 진리표
  
    $$
    \begin{array}{|c c|c|}
    p & q & p\land q\\
    \hline
    T & T & T\\
    T & F & F\\
    F & T & F\\
    F & F & F\\
    \end{array}
    $$
  
  - 예)
    - $$p$$: 지구는 태양의 행성이다.($$T$$)
    - $$q$$: 달의 실제 크기는 지구보다 크다.($$F$$)
    - $$p \land q$$: 지구는 태양의 행성이다. 그리고 달의 실제 크기는 지구보다 크다.($$F$$)

## 논리합

- 논리합(or): $$p \lor q$$
  - 이항 연산자
  - $$p$$ 또는 $$q$$
  - 진리표
  
    $$
    \begin{array}{|c c|c|}
    p & q & p\lor q\\
    \hline
    T & T & T\\
    T & F & T\\
    F & T & T\\
    F & F & F\\
    \end{array}
    $$

  - 예)
    - $$p$$: 지구는 태양의 행성이다.($$T$$)
    - $$q$$: 달의 실제 크기는 지구보다 크다.($$F$$)
    - $$p \lor q$$: 지구는 태양의 행성이다. 또는 달의 실제 크기는 지구보다 크다.($$T$$)

## 배타적 논리합

- 배타적 논리합(xor): $$p \oplus q$$
  - 이항 연산자
  - 같으면 $$F$$, 다르면 $$T$$
  - $$p \oplus q \equiv (\neg p \land q) \lor (p \land \neg q)$$처럼 연산
  - 진리표
  
    $$
    \begin{array}{|c c|c|}
    p & q & p\oplus q\\
    \hline
    T & T & F\\
    T & F & T\\
    F & T & T\\
    F & F & F\\
    \end{array}
    $$

# 3. 조건 명제

- 조건 명제(conditional proposition): $$p \rightarrow q$$
  - 이항 연산자
  - $$p$$​이면 $$q$$​​​이다.
  - $$p \rightarrow q \equiv \neg(p \land \neg q)$$처럼 연산
  - 진리표

    $$
    \begin{array}{|c c|c|}
    p & q & p\rightarrow q\\
    \hline
    T & T & T\\
    T & F & F\\
    F & T & T\\
    F & F & T\\
    \end{array}
    $$

  - 예)
    - $$p$$: $$1 + 2 = 5$$($$F$$)
    - $$q$$: $$2 + 3 = 5$$($$T$$​)
    - $$p \rightarrow q$$: $$1 + 2 = 5$$이면 $$2 + 3 = 5$$($$T$$)

- 역(converse)
  - 조건 명제 $$p \rightarrow q$$에 대하여, $$q \rightarrow p$$
  - 예)
    - $$p$$: .지구의 자전축은 기울어져 있다.
    - $$q$$: 지구의 계절이 바뀐다.
    - $$p \rightarrow q$$: 지구의 자전축이 기울어져 있다면, 지구의 계절은 바뀐다.
    - $$q \rightarrow p$$: 지구의 계절이 바뀐다면 지구의 자전축은 기울어져 있다.

- 이(inverse)
  - 조건 명제 $$p \rightarrow q$$에 대하여, $$\neg p \rightarrow \neg q$$

- 대우(contraposition)
  - 조건 명제 $$p \rightarrow q$$에 대하여, $$\neg q \rightarrow \neg p$$​
  - 역과 이를 모두 연산한 결과
  - $$p \rightarrow q$$​의 진리값와 대우의 진리값은 같음

## 쌍방조건 명제

- 쌍방건 명제(biconditional proposition): $$p \leftrightarrow q$$

  - 이항 연산자
  - $$p$$이면 $$q$$이며, 반대도 성립한다.
  - $$p$$는 $$q$$​의 필요충분조건
  - $$p \leftrightarrow q \equiv (p \rightarrow q) \land (q \rightarrow p)$$​처럼 연산
    - $$p \leftrightarrow q \equiv \neg(p \oplus q)$$처럼도 가능
  - 진리표
    $$
    \begin{array}{|c c|c|}
    p & q & p\leftrightarrow q\\
    \hline
    T & T & T\\
    T & F & F\\
    F & T & F\\
    F & F & T\\
    \end{array}
    $$
    

# 4. 합성 명제

## 논리 연산자의 우선순위

1. $$\neg$$(not)
2. $$\land$$(and)
3. $$\lor$$(or)
4. $$\oplus$$(xor)
5. $$\rightarrow$$(implies)
6. $$\leftrightarrow$$(biconditional)

- 예)
  - 합성 명제: $$\neg (p \land q) \oplus (\neg p \lor q)$$
  - 진리표
  
    $$
    \begin{array}{|c|c|c|c|c|c|c|}
    p & q & \neg p & p \land q & \neg (p \land q) & \neg p \lor q & \neg (p \land q) \oplus (\neg p \lor q) \\
    \hline
    T & T & F & T & F & T & T \\
    T & F & F & F & T & F & T \\
    F & T & T & F & T & T & T \\
    F & F & T & F & T & T & F \\
    
    \end{array}
    $$

## 합성 명제의 종류

- 항진 명제(tautology, $$\mathcal{T}$$​)
  - 진리값에 상관 없이 합성 명제의 진리값이 항상 참인 명제
  - 예)
    - 합성 명제: $$p \lor \neg p$$
    - 진리표
    
      $$
      \begin{array}{|c c|c|}
      p & \neg p & p \lor \neg p\\
      \hline
      T & F & T\\
      F & T & T\\
      \end{array}
      $$
      

- 모순 명제(contradiction, $$\mathcal{F}$$)
  - 진리값에 상관 없이 합성 명제의 진리값이 항상 거짓인 명제
  - 예)
    - 합성 명제: $$p \land \neg p$$
    - 진리표
    
      $$
      \begin{array}{|c c|c|}
      p & \neg p & p \land \neg p\\
      \hline
      T & F & F\\
      F & T & F\\
      \end{array}
      $$

- 사건 명제(contingency)
  - 항진 명제도, 모순 명제도 아닌 합성 명제

# 5. 논리적 동치

- 논리적 동치(logically equivalence, $$P \equiv Q$$)
  - 두 합성 명제의 진리값이 같은 경우

## 진리표를 이용한 증명

- xor: $$p \oplus q \equiv (\neg p \land q) \lor (p \land \neg q)$$
- 진리표

  $$
  \begin{array}{|c|c|c|c|c|c|c|c|}
  p & q & \neg p & \neg q & \neg p \land q & p \land \neg q & (\neg p \land q) \lor (p \land \neg q) & p \oplus q \\
  \hline
  T & T & F & F & F & F & F & F \\
  T & F & F & T & F & T & T & T \\
  F & T & T & F & T & F & T & T \\
  F & F & T & T & F & F & F & F \\
  \end{array}
  $$

  - 오른쪽 두 합성 명제의 진리값이 완전히 같으므로 동치

## 논리적 동치법칙을 이용한 증명

### 항등법칙(Identity Laws)
- \$ p \land \mathcal{T} \equiv p $
- \$ p \lor \mathcal{F} \equiv p $

### 지배법칙(Domination Laws)
- \$ p \land \mathcal{F} \equiv \mathcal{F} $
- \$ p \lor \mathcal{T} \equiv \mathcal{T} $

### 부정법칙(Negation Laws)
- \$ p \land \neg p \equiv \mathcal{F} $
- \$ p \lor \neg p \equiv \mathcal{T} $

### 이중 부정법칙(Double Negation Law)
- \$ \neg(\neg p) \equiv p $

### 멱등법칙(Idempotent Laws)
- \$ p \land p \equiv p $
- \$ p \lor p \equiv p $

### 교환법칙(Commutative Laws)
- \$ p \land q \equiv q \land p $
- \$ p \lor q \equiv q \lor p $

### 결합법칙(Associative Laws)
- \$ (p \land q) \land r \equiv p \land (q \land r) $
- \$ (p \lor q) \lor r \equiv p \lor (q \lor r) $

### 분배법칙(Distributive Laws)
- \$ p \land (q \lor r) \equiv (p \land q) \lor (p \land r) $
- \$ p \lor (q \land r) \equiv (p \lor q) \land (p \lor r) $

### 드모르간의 법칙(De Morgan's Laws)
- \$ \neg(p \land q) \equiv \neg p \lor \neg q $
- \$ \neg(p \lor q) \equiv \neg p \land \neg q $

### 흡수법칙(Absorption Laws)
- \$ p \lor (p \land q) \equiv p $
- \$ p \land (p \lor q) \equiv p $

### 합축법칙(Consensus Theorem)
- \$ (p \land q) \lor (\neg p \land r) \lor (q \land r) \equiv (p \land q) \lor (\neg p \land r) $

### 예) 흡수법칙 증명

$$
\begin{align*}
p \lor (p \land q) &\equiv (p \lor \mathcal{F}) \land (p \lor q) && (\because \text{Identity Laws})\\
& \equiv p \lor (\mathcal{F} \land q) && (\because \text{Distributive Laws})\\
& \equiv p \lor \mathcal{F} && (\because \text{Domination Laws})\\
& \equiv p && (\because \text{Identity Laws})\\
\end{align*}
$$

# 6. 명제 함수와 한정자

## 명제 함수

- 명제 함수(propositional function, $$P(x)$$)
  - 논의 영역이 주어진 변수 $$x$$를 포함하여 진리값을 판별할 수 있는 문장
- 논의 영역(domain of discource, $$D$$)
  - 변수 $$x$$의 범위나 값
- 예)
  - $$x=3$$일 때, $$P(x): x^2-3x=0$$($$T$$)
  - $$x=-5, y=1$$일 때, $$Q(x, y): x \gt 3y$$($$F$$)

## 한정자

- 전체 한정자(universal quantifier, $$\forall$$)
  - 논의 영역 $$D$$에 포함되는 모든 값 중 전체
  - 모든 $$x$$에 대하여 $$P(x)$$이다.($$\forall x P(x)$$)
  - 예) 논의 영역 $$D$$가 정수 집합($$\mathbb{R}$$)일 때
    - $$P(x)$$: $$x$$는 실수이다. $$\forall x P(x)$$: $$F$$
    - $$P(x)$$: $$x$$는 자연수이다. $$\forall x P(x)$$: $$T$$
- 존재 한정자(existential quantifier, $$\exists$$)
  - 논의 영역 $$D$$에 포함되는 모든 값 중 일부
  - 어떤 $$x$$에 대하여 $$P(x)$이다.($$$$\exists x P(x)$$)
  - 예) 논의 영역 $$D$$가 정수 집합($$\mathbb{R}$$)일 때
    - $$P(x)$$: $$x$$는 실수이다. $$\exists x P(x)$$: $$T$$
    - $$P(x)$$: $$x$$​는 허수이다. $$\exists x P(x)$$: $$F$$​
- 한정자와 논리곱, 논리합
  - 논리곱: $$\forall x(P(x) \land Q(x)) \equiv \forall x P(x) \land \forall x Q(x)$$
  - 논리합: $$\exists x(P(x) \lor Q(x)) \equiv \exists x P(x) \lor \exists Q(x)$$
- 한정자와 부정
  - \$\neg(\forall x P(x)) \equiv \exists x(\neg P(x))$
  - \$\neg(\exists x P(x)) \equiv \forall x(\neg P(x))$
  - 예) $$D$$: 과일, $$P(x)$$: 이 상자에 있는 $$x$$는 사과이다.
    - $$\forall x P(x)$$: 이 상자에 있는 모든 과일은 사과이다.
      - $$\exists x(\neg P(x))$$: 이 상자에 있는 어떤 과일은 사과가 아니다.
    - $$ \exists x P(x)$$: 이 상자에 있는 어떤 과일은 사과이다.
      - $$\forall x(\neg P(x))$$: 이 상자에 있는 모든 과일은 사과가 아니다.

# 7. 추론

- 추론(inference), 논증(reasoning)
  - 참인 명제를 근거로 하여 다른 명제가 참임을 유도하는 과정
- 전체(hypothesis)와 결론(conclusion)
  - 전제: 결론의 근거가 되는 참인 명제
  - 결론: 주어진 전제에 의해 유도된 최종적인 참인 명제

## 유효 추론과 허위 추론

- 유효 추론(valid inference)
  - 진리값이 참인 전제를 이용해 유도한 결론이 모두 참인 추론
  - 예)
  
    1. **모든 A는 B이다. X는 A이다. 그러므로 X는 B이다.**
       - 예: 모든 사람은 동물이다. 철수는 사람이다. 따라서 철수는 동물이다.
  
    2. **A가 B와 C에 모두 속한다. 그러므로 A는 B와 C가 같다.**
       - 예: 사과는 과일이며 책상 위에 있다. 따라서 사과는 과일이자 책상 위에 있다.
  
    3. **A가 B에 속하고 B가 C에 속한다면, A는 C에 속한다.**
       - 예: 강아지는 동물에 속하고 동물은 생물에 속한다. 따라서 강아지는 생물에 속한다.
  
    4. **A와 B가 동등하다면, B와 C가 동등하면 A와 C도 동등하다.**
       - 예: 2는 4와 동등하고 4는 6과 동등하다면, 2는 6과 동등하다.
  
    5. **일반화된 패턴을 사용하여 결론을 도출하는 추론.**
       
       - 예: 모든 포유류는 동물이다. 고양이는 포유류이다. 따라서 고양이는 동물이다.
    6. **A면 B이다. A는 참이다. 그러므로 B는 참이다.**
       - 예: 철수가 성인이면 철수는 주민등록증이 있다., 철수는 성인이다. 따라서 철수는 주민등록증이 있다.
       - 추론
       
         $$
         \begin{align*}
         & p \rightarrow q\\
         & p\\
         & \;\;\;\;\therefore q
         \end{align*}
         $$
         
       - 진리표
    
         $$
         \begin{array}{|c c|c|}
         p\rightarrow q & p & q\\
         \hline
         T & T & T\\
         F & T & F\\
         T & F & T\\
         T & F & F\\
         \end{array}
         $$
       
         - 두 전제 $$p \rightarrow q$$와 $$p$$가 $$T$$일 때, 결론 $$q$$는 $$T$$​
         - 따라서 추론은 유효
       
  
- 허위 추론(fallacious inference)
  - 진리값이 참인 전제를 이용해 유도한 결론이 거짓인 추론
  - 예)
    - 철수가 중학생이면 청소년이다. 철수는 청소년이다. 따라서 철수는 중학생이다.
    - 추론
    
      $$
      \begin{align*}
      & p \rightarrow q\\
      & q\\
      & \;\;\;\;\therefore p
      \end{align*}
      $$
      
    - 진리표

      $$
      \begin{array}{|c c|c|}
      p\rightarrow q & q & p\\
      \hline
      T & T & T\\
      F & F & T\\
      T & T & F\\
      T & F & F\\
      \end{array}
      $$

      - 두 전제 $$p \rightarrow q$$와 $$q$$가 $$T$$일 때, 결론 $$p$$는 $$T$$이거나 $$F$$

      - 따라서 추론은 허위
    

## 논리적 추론법칙

### 논리곱(conjunction)

- 추론
  $$
  \begin{align*}
  & p\\
  & q\\
  & \;\;\;\;\therefore p \land q
  \end{align*}
  $$
  
- 항진 명제

  $$
  (p \land q) \rightarrow (p\land q)
  $$

### 선언적 부가(disjunctive addition)

- 추론
  $$
  \begin{align*}
  & p\\
  & \;\;\;\;\therefore p \lor q
  \end{align*}
  $$
  
- 항진 명제

  $$
  p \rightarrow (p \lor q)
  $$

### 단순화(simplication)

- 추론
  $$
  \begin{align*}
  & p \land q\\
  & \;\;\;\;\therefore p(\text{or}\;q)
  \end{align*}
  $$
  
- 항진 명제

  $$
  (p \land q) \rightarrow p(\text{or}\;q)
  $$
  
### 긍정논법(modus ponens)

- 추론
  $$
  \begin{align*}
  & p\\
  & p \rightarrow q\\
  & \;\;\;\;\therefore q
  \end{align*}
  $$
  
- 항진 명제

  $$
  \left\{ p \land (p \rightarrow q) \right\} \rightarrow q
  $$
  
### 부정논법(modus tollens)

- 추론
  $$
  \begin{align*}
  & \neg q\\
  & p \rightarrow q\\
  & \;\;\;\;\therefore \neg p
  \end{align*}
  $$
  
- 항진 명제

  $$
  
  $$
  
### 선언적 삼단논법, 소거(disjunctive syllogism)

- 추론
  $$
  \begin{align*}
  & p \lor q\\
  & \neg q\\
  & \;\;\;\;\therefore p
  \end{align*}
  $$
  
- 항진 명제

  $$
  \left\{ (p \lor q) \land \neg q \right\} \rightarrow p
  $$
  
### 가설적 삼단논법, 추이(hypothetical syllogism)

- 추론
  $$
  \begin{align*}
  & p \rightarrow q\\
  & q \rightarrow r\\
  & \;\;\;\;\therefore p \rightarrow r
  \end{align*}
  $$
  
- 항진 명제

  $$
  \left\{ (p \rightarrow q) \land (q \rightarrow r) \right\} \rightarrow (p \rightarrow r)
  $$