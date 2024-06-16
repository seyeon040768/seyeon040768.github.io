---
title: 이산수학 9. 그래프
author: seyeon
date: 2024-06-16 02:00:00 +0900
categories: [Math, Discrete Mathematics]
tags: [discrete]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-06-16-discrete-mathematics-9/discrete_mathematics_main.jpg
  lqip: data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEASABIAAD/4gxYSUNDX1BST0ZJTEUAAQEAAAxITGlubwIQAABtbnRyUkdCIFhZWiAHzgACAAkABgAxAABhY3NwTVNGVAAAAABJRUMgc1JHQgAAAAAAAAAAAAAAAAAA9tYAAQAAAADTLUhQICAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABFjcHJ0AAABUAAAADNkZXNjAAABhAAAAGx3dHB0AAAB8AAAABRia3B0AAACBAAAABRyWFlaAAACGAAAABRnWFlaAAACLAAAABRiWFlaAAACQAAAABRkbW5kAAACVAAAAHBkbWRkAAACxAAAAIh2dWVkAAADTAAAAIZ2aWV3AAAD1AAAACRsdW1pAAAD+AAAABRtZWFzAAAEDAAAACR0ZWNoAAAEMAAAAAxyVFJDAAAEPAAACAxnVFJDAAAEPAAACAxiVFJDAAAEPAAACAx0ZXh0AAAAAENvcHlyaWdodCAoYykgMTk5OCBIZXdsZXR0LVBhY2thcmQgQ29tcGFueQAAZGVzYwAAAAAAAAASc1JHQiBJRUM2MTk2Ni0yLjEAAAAAAAAAAAAAABJzUkdCIElFQzYxOTY2LTIuMQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAWFlaIAAAAAAAAPNRAAEAAAABFsxYWVogAAAAAAAAAAAAAAAAAAAAAFhZWiAAAAAAAABvogAAOPUAAAOQWFlaIAAAAAAAAGKZAAC3hQAAGNpYWVogAAAAAAAAJKAAAA+EAAC2z2Rlc2MAAAAAAAAAFklFQyBodHRwOi8vd3d3LmllYy5jaAAAAAAAAAAAAAAAFklFQyBodHRwOi8vd3d3LmllYy5jaAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABkZXNjAAAAAAAAAC5JRUMgNjE5NjYtMi4xIERlZmF1bHQgUkdCIGNvbG91ciBzcGFjZSAtIHNSR0IAAAAAAAAAAAAAAC5JRUMgNjE5NjYtMi4xIERlZmF1bHQgUkdCIGNvbG91ciBzcGFjZSAtIHNSR0IAAAAAAAAAAAAAAAAAAAAAAAAAAAAAZGVzYwAAAAAAAAAsUmVmZXJlbmNlIFZpZXdpbmcgQ29uZGl0aW9uIGluIElFQzYxOTY2LTIuMQAAAAAAAAAAAAAALFJlZmVyZW5jZSBWaWV3aW5nIENvbmRpdGlvbiBpbiBJRUM2MTk2Ni0yLjEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAHZpZXcAAAAAABOk/gAUXy4AEM8UAAPtzAAEEwsAA1yeAAAAAVhZWiAAAAAAAEwJVgBQAAAAVx/nbWVhcwAAAAAAAAABAAAAAAAAAAAAAAAAAAAAAAAAAo8AAAACc2lnIAAAAABDUlQgY3VydgAAAAAAAAQAAAAABQAKAA8AFAAZAB4AIwAoAC0AMgA3ADsAQABFAEoATwBUAFkAXgBjAGgAbQByAHcAfACBAIYAiwCQAJUAmgCfAKQAqQCuALIAtwC8AMEAxgDLANAA1QDbAOAA5QDrAPAA9gD7AQEBBwENARMBGQEfASUBKwEyATgBPgFFAUwBUgFZAWABZwFuAXUBfAGDAYsBkgGaAaEBqQGxAbkBwQHJAdEB2QHhAekB8gH6AgMCDAIUAh0CJgIvAjgCQQJLAlQCXQJnAnECegKEAo4CmAKiAqwCtgLBAssC1QLgAusC9QMAAwsDFgMhAy0DOANDA08DWgNmA3IDfgOKA5YDogOuA7oDxwPTA+AD7AP5BAYEEwQgBC0EOwRIBFUEYwRxBH4EjASaBKgEtgTEBNME4QTwBP4FDQUcBSsFOgVJBVgFZwV3BYYFlgWmBbUFxQXVBeUF9gYGBhYGJwY3BkgGWQZqBnsGjAadBq8GwAbRBuMG9QcHBxkHKwc9B08HYQd0B4YHmQesB78H0gflB/gICwgfCDIIRghaCG4IggiWCKoIvgjSCOcI+wkQCSUJOglPCWQJeQmPCaQJugnPCeUJ+woRCicKPQpUCmoKgQqYCq4KxQrcCvMLCwsiCzkLUQtpC4ALmAuwC8gL4Qv5DBIMKgxDDFwMdQyODKcMwAzZDPMNDQ0mDUANWg10DY4NqQ3DDd4N+A4TDi4OSQ5kDn8Omw62DtIO7g8JDyUPQQ9eD3oPlg+zD88P7BAJECYQQxBhEH4QmxC5ENcQ9RETETERTxFtEYwRqhHJEegSBxImEkUSZBKEEqMSwxLjEwMTIxNDE2MTgxOkE8UT5RQGFCcUSRRqFIsUrRTOFPAVEhU0FVYVeBWbFb0V4BYDFiYWSRZsFo8WshbWFvoXHRdBF2UXiReuF9IX9xgbGEAYZRiKGK8Y1Rj6GSAZRRlrGZEZtxndGgQaKhpRGncanhrFGuwbFBs7G2MbihuyG9ocAhwqHFIcexyjHMwc9R0eHUcdcB2ZHcMd7B4WHkAeah6UHr4e6R8THz4faR+UH78f6iAVIEEgbCCYIMQg8CEcIUghdSGhIc4h+yInIlUigiKvIt0jCiM4I2YjlCPCI/AkHyRNJHwkqyTaJQklOCVoJZclxyX3JicmVyaHJrcm6CcYJ0kneierJ9woDSg/KHEooijUKQYpOClrKZ0p0CoCKjUqaCqbKs8rAis2K2krnSvRLAUsOSxuLKIs1y0MLUEtdi2rLeEuFi5MLoIuty7uLyQvWi+RL8cv/jA1MGwwpDDbMRIxSjGCMbox8jIqMmMymzLUMw0zRjN/M7gz8TQrNGU0njTYNRM1TTWHNcI1/TY3NnI2rjbpNyQ3YDecN9c4FDhQOIw4yDkFOUI5fzm8Ofk6Njp0OrI67zstO2s7qjvoPCc8ZTykPOM9Ij1hPaE94D4gPmA+oD7gPyE/YT+iP+JAI0BkQKZA50EpQWpBrEHuQjBCckK1QvdDOkN9Q8BEA0RHRIpEzkUSRVVFmkXeRiJGZ0arRvBHNUd7R8BIBUhLSJFI10kdSWNJqUnwSjdKfUrESwxLU0uaS+JMKkxyTLpNAk1KTZNN3E4lTm5Ot08AT0lPk0/dUCdQcVC7UQZRUFGbUeZSMVJ8UsdTE1NfU6pT9lRCVI9U21UoVXVVwlYPVlxWqVb3V0RXklfgWC9YfVjLWRpZaVm4WgdaVlqmWvVbRVuVW+VcNVyGXNZdJ114XcleGl5sXr1fD19hX7NgBWBXYKpg/GFPYaJh9WJJYpxi8GNDY5dj62RAZJRk6WU9ZZJl52Y9ZpJm6Gc9Z5Nn6Wg/aJZo7GlDaZpp8WpIap9q92tPa6dr/2xXbK9tCG1gbbluEm5rbsRvHm94b9FwK3CGcOBxOnGVcfByS3KmcwFzXXO4dBR0cHTMdSh1hXXhdj52m3b4d1Z3s3gReG54zHkqeYl553pGeqV7BHtje8J8IXyBfOF9QX2hfgF+Yn7CfyN/hH/lgEeAqIEKgWuBzYIwgpKC9INXg7qEHYSAhOOFR4Wrhg6GcobXhzuHn4gEiGmIzokziZmJ/opkisqLMIuWi/yMY4zKjTGNmI3/jmaOzo82j56QBpBukNaRP5GokhGSepLjk02TtpQglIqU9JVflcmWNJaflwqXdZfgmEyYuJkkmZCZ/JpomtWbQpuvnByciZz3nWSd0p5Anq6fHZ+Ln/qgaaDYoUehtqImopajBqN2o+akVqTHpTilqaYapoum/adup+CoUqjEqTepqaocqo+rAqt1q+msXKzQrUStuK4trqGvFq+LsACwdbDqsWCx1rJLssKzOLOutCW0nLUTtYq2AbZ5tvC3aLfguFm40blKucK6O7q1uy67p7whvJu9Fb2Pvgq+hL7/v3q/9cBwwOzBZ8Hjwl/C28NYw9TEUcTOxUvFyMZGxsPHQce/yD3IvMk6ybnKOMq3yzbLtsw1zLXNNc21zjbOts83z7jQOdC60TzRvtI/0sHTRNPG1EnUy9VO1dHWVdbY11zX4Nhk2OjZbNnx2nba+9uA3AXcit0Q3ZbeHN6i3ynfr+A24L3hROHM4lPi2+Nj4+vkc+T85YTmDeaW5x/nqegy6LzpRunQ6lvq5etw6/vshu0R7ZzuKO6070DvzPBY8OXxcvH/8ozzGfOn9DT0wvVQ9d72bfb794r4Gfio+Tj5x/pX+uf7d/wH/Jj9Kf26/kv+3P9t////2wBDAAQCAwMDAgQDAwMEBAQEBQkGBQUFBQsICAYJDQsNDQ0LDAwOEBQRDg8TDwwMEhgSExUWFxcXDhEZGxkWGhQWFxb/2wBDAQQEBAUFBQoGBgoWDwwPFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhb/wAARCAAKAA8DASIAAhEBAxEB/8QAFgABAQEAAAAAAAAAAAAAAAAABgMH/8QAJRAAAgECBQQDAQAAAAAAAAAAAQIDBAUABhESMSEiQVEHEzJC/8QAFQEBAQAAAAAAAAAAAAAAAAAABgf/xAAcEQACAgIDAAAAAAAAAAAAAAABAwARBBMhIlH/2gAMAwEAAhEDEQA/AJ3qpzpkO5yihpTU5fjcyxmIBlC87COVY/n13A+8KMvfI9ruVtM00J3qvaafVvsJbaoC9ddwjlcafyAfOE0yq4ZHAZW7WBGoIPIOMOtzNRx3SajY08kNMzxPEdhjY1mwlSOCUVV6eABwMEl9rBlUzGbVhpFEecXP/9k=
  alt: Unsplash의 Philip Oroni
  
typora-root-url: ../
---

# 1. 그래프의 개념

- 그래프(graph, $$G=(V, E)$$): 정점의 집합 $$V$$와 변의 집합 $$E$$로 구성된 구조
  - 정점 $$v_i$$와 $$v_j$$는 인접(adjacent): $$v_i$$와 $$v_j$$를 연결하는 변이 존재
  - 변 $$e_k$$는 정점 $$v_i$$와 $$v_j$$에 근접(incident): $$e_k$$는 $$v_i$$와 $$v_j$$를 연결
- 단순 그래프(simple graph): 임의의 두 정점 사이에 오직 하나의 변이 있는 그래프
- 다중 그래프(multi graph): 임의의 두 정점 사이에 두 개 이상의 변이 있는 그래프
- 방향 그래프(directed graph, $$G = <V, E>$$): 정점 사이에 순서가 존재하여 화살표를 이용해 표현하는 그래프
- 가중치 그래프(weighted graph): 각 변에 가중치가 부여된 그래프
  - $$W[v_i, v_j]$$: $$v_i$$와 $$v_j$$에 근접하는 변에 부여된 가중치
- 차수(degree, $$d(v)$$): $$v$$에 근접하는 변의 개수
  - 외차수(out-degree, $$d_{out}(v)$$): $$v$$를 시작점으로 하는 화살표의 개수
  - 내차수(in-degree, $$d_{in}(v)$$): $$v$$를 끝점으로 하는 화살표의 개수
  - 모든 정점의 차수의 합은 변의 개수의 2배
  - 차수가 홀수인 정점의 개수는 짝수

# 2. 그래프의 종류

- 부분 그래프(subgraph): $$V^\prime \subseteq V$$이고 $$E^\prime \subseteq E$$인 정점과 변으로 구성된 $$G \neq G^\prime$$인 그래프
- 신장부분 그래프(spanning subgraph): $$V^\prime = V$$이고 $$E^\prime \subseteq E$$인 정점과 변으로 구성된 그래프
- 동형 그래프(isomorphic graph): $$G_1 = (V_1, E_1)$$과 $$G_2 = (V_2, E_2)$$에 대한 함수 $$f: V_1 \rightarrow V_2$$가 $$u, v \in V_1$$에 대하여 $$(u, v) \in E_1$$이면 $$(f(u), f(v)) \in E_2$$를 만족하는 전단사 함수일 때, 두 그래프 $$G_1$$, $$G_2$$
- 연결 그래프(connected graph): 임의의 정점 $$u, v$$ 사이에 경로가 있는 그래프(소외된 부분 그래프가 없는 그래프)
- 경로(path): 임의의 정점 $$u, v$$ 사이에 가능한 길 중에서 같은 변을 두 번 이상 포함하지 않는 길
- 평면 그래프(planar graph): 연결 그래프를 평면에 그릴 때 어떤 변도 교차하지 않도록 그릴 수 있는 그래프
- 오일러 공식: 평면 그래프에서 정점의 수를 $$v$$, 변의 수를 $$e$$, 영역의 수를 $$s$$라고 할 때, $$v - e + s = 2$$
- 정규 그래프(regular graph, $$k$$-정규그래프): 모든 정점의 차수가 $$k$$로 같은 그래프
- 완전 그래프(complete graph, $$K_n$$): 모든 정점 사이에 변이 존재하는 그래프
- 완전이분 그래프(complete bipartite graph, $$K_{m, n}$$): 정점 집합 $$V$$에서 $$V = V_1 \cup V_2$$와 $$V_1 \cap V_2 = \varnothing$$을 만족하는 $$V_1$$과 $$V_2$$에 대해, **모든** 변이 $$V_1$$의 한 정점에서 $$V_2$$의 한 정점으로 연결되는 그래프
- 이분 그래프(bipartite graph): 정점 집합 $$V$$에서 $$V = V_1 \cup V_2$$와 $$V_1 \cap V_2 = \varnothing$$을 만족하는 $$V_1$$과 $$V_2$$에 대해, **어떤** 변이 $$V_1$$의 한 정점에서 $$V_2$$의 한 정점으로 연결되는 그래프

# 3. 그래프의 표현

- 인접 행렬(adjacency matrix, $$A_G$$)

  $$
  a_{ij} =
  \begin{cases}
  \text{해당 정점에 근접하는 변의 수}&,(v_i, v_j)\in E\\
  0&, (v_i, v_j) \notin E\\
  \end{cases}
  $$

- 인접 리스트(adjacency list): 각 정점에 인접하는 정점들을 연결리스트로 표현한 것

# 4. 오일러와 해밀턴

- 순환(cycle): 연결 그래프에서 시작하는 정점과 끝나는 정점이 같은 경로
- 길이(length): 경로를 구성하는 변의 수
- 오일러 경로(Eulerian path): 임의의 정점에서 시작하여 모든 변을 한 번씩만 지나는 경로
  - 오일러 순환(Eulerian cycle): 오일러 경로이면서 순환하는 경로
  - 오일러 그래프(Eulerian graph): 오일러 순환을 가지는 그래프
    - 정점 중 차수가 홀수인 정점의 수가 0 또는 2개인 그래프
- 해밀턴 경로(Hamiltonian path): 모든 정점을 한 번씩만 지나는 경로
  - 해밀턴 순환(Hamiltonian cycle): 해밀턴 경로이면서 순환하는 경로
  - 해밀턴 그래프(Hamiltonian graph): 해밀턴 순환을 가지는 그래프



