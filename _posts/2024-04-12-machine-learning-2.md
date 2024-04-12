---
title: 머신러닝 2. 모델 평가 및 선택
author: seyeon
date: 2024-04-12 01:00:00 +0900
categories: [Artificial Intelligence, Machine Learning]
tags: [ml]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-04-12-machine-learning-2/machine-learning-main.jpg
  lqip: data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEASABIAAD/4gxYSUNDX1BST0ZJTEUAAQEAAAxITGlubwIQAABtbnRyUkdCIFhZWiAHzgACAAkABgAxAABhY3NwTVNGVAAAAABJRUMgc1JHQgAAAAAAAAAAAAAAAAAA9tYAAQAAAADTLUhQICAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABFjcHJ0AAABUAAAADNkZXNjAAABhAAAAGx3dHB0AAAB8AAAABRia3B0AAACBAAAABRyWFlaAAACGAAAABRnWFlaAAACLAAAABRiWFlaAAACQAAAABRkbW5kAAACVAAAAHBkbWRkAAACxAAAAIh2dWVkAAADTAAAAIZ2aWV3AAAD1AAAACRsdW1pAAAD+AAAABRtZWFzAAAEDAAAACR0ZWNoAAAEMAAAAAxyVFJDAAAEPAAACAxnVFJDAAAEPAAACAxiVFJDAAAEPAAACAx0ZXh0AAAAAENvcHlyaWdodCAoYykgMTk5OCBIZXdsZXR0LVBhY2thcmQgQ29tcGFueQAAZGVzYwAAAAAAAAASc1JHQiBJRUM2MTk2Ni0yLjEAAAAAAAAAAAAAABJzUkdCIElFQzYxOTY2LTIuMQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAWFlaIAAAAAAAAPNRAAEAAAABFsxYWVogAAAAAAAAAAAAAAAAAAAAAFhZWiAAAAAAAABvogAAOPUAAAOQWFlaIAAAAAAAAGKZAAC3hQAAGNpYWVogAAAAAAAAJKAAAA+EAAC2z2Rlc2MAAAAAAAAAFklFQyBodHRwOi8vd3d3LmllYy5jaAAAAAAAAAAAAAAAFklFQyBodHRwOi8vd3d3LmllYy5jaAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABkZXNjAAAAAAAAAC5JRUMgNjE5NjYtMi4xIERlZmF1bHQgUkdCIGNvbG91ciBzcGFjZSAtIHNSR0IAAAAAAAAAAAAAAC5JRUMgNjE5NjYtMi4xIERlZmF1bHQgUkdCIGNvbG91ciBzcGFjZSAtIHNSR0IAAAAAAAAAAAAAAAAAAAAAAAAAAAAAZGVzYwAAAAAAAAAsUmVmZXJlbmNlIFZpZXdpbmcgQ29uZGl0aW9uIGluIElFQzYxOTY2LTIuMQAAAAAAAAAAAAAALFJlZmVyZW5jZSBWaWV3aW5nIENvbmRpdGlvbiBpbiBJRUM2MTk2Ni0yLjEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAHZpZXcAAAAAABOk/gAUXy4AEM8UAAPtzAAEEwsAA1yeAAAAAVhZWiAAAAAAAEwJVgBQAAAAVx/nbWVhcwAAAAAAAAABAAAAAAAAAAAAAAAAAAAAAAAAAo8AAAACc2lnIAAAAABDUlQgY3VydgAAAAAAAAQAAAAABQAKAA8AFAAZAB4AIwAoAC0AMgA3ADsAQABFAEoATwBUAFkAXgBjAGgAbQByAHcAfACBAIYAiwCQAJUAmgCfAKQAqQCuALIAtwC8AMEAxgDLANAA1QDbAOAA5QDrAPAA9gD7AQEBBwENARMBGQEfASUBKwEyATgBPgFFAUwBUgFZAWABZwFuAXUBfAGDAYsBkgGaAaEBqQGxAbkBwQHJAdEB2QHhAekB8gH6AgMCDAIUAh0CJgIvAjgCQQJLAlQCXQJnAnECegKEAo4CmAKiAqwCtgLBAssC1QLgAusC9QMAAwsDFgMhAy0DOANDA08DWgNmA3IDfgOKA5YDogOuA7oDxwPTA+AD7AP5BAYEEwQgBC0EOwRIBFUEYwRxBH4EjASaBKgEtgTEBNME4QTwBP4FDQUcBSsFOgVJBVgFZwV3BYYFlgWmBbUFxQXVBeUF9gYGBhYGJwY3BkgGWQZqBnsGjAadBq8GwAbRBuMG9QcHBxkHKwc9B08HYQd0B4YHmQesB78H0gflB/gICwgfCDIIRghaCG4IggiWCKoIvgjSCOcI+wkQCSUJOglPCWQJeQmPCaQJugnPCeUJ+woRCicKPQpUCmoKgQqYCq4KxQrcCvMLCwsiCzkLUQtpC4ALmAuwC8gL4Qv5DBIMKgxDDFwMdQyODKcMwAzZDPMNDQ0mDUANWg10DY4NqQ3DDd4N+A4TDi4OSQ5kDn8Omw62DtIO7g8JDyUPQQ9eD3oPlg+zD88P7BAJECYQQxBhEH4QmxC5ENcQ9RETETERTxFtEYwRqhHJEegSBxImEkUSZBKEEqMSwxLjEwMTIxNDE2MTgxOkE8UT5RQGFCcUSRRqFIsUrRTOFPAVEhU0FVYVeBWbFb0V4BYDFiYWSRZsFo8WshbWFvoXHRdBF2UXiReuF9IX9xgbGEAYZRiKGK8Y1Rj6GSAZRRlrGZEZtxndGgQaKhpRGncanhrFGuwbFBs7G2MbihuyG9ocAhwqHFIcexyjHMwc9R0eHUcdcB2ZHcMd7B4WHkAeah6UHr4e6R8THz4faR+UH78f6iAVIEEgbCCYIMQg8CEcIUghdSGhIc4h+yInIlUigiKvIt0jCiM4I2YjlCPCI/AkHyRNJHwkqyTaJQklOCVoJZclxyX3JicmVyaHJrcm6CcYJ0kneierJ9woDSg/KHEooijUKQYpOClrKZ0p0CoCKjUqaCqbKs8rAis2K2krnSvRLAUsOSxuLKIs1y0MLUEtdi2rLeEuFi5MLoIuty7uLyQvWi+RL8cv/jA1MGwwpDDbMRIxSjGCMbox8jIqMmMymzLUMw0zRjN/M7gz8TQrNGU0njTYNRM1TTWHNcI1/TY3NnI2rjbpNyQ3YDecN9c4FDhQOIw4yDkFOUI5fzm8Ofk6Njp0OrI67zstO2s7qjvoPCc8ZTykPOM9Ij1hPaE94D4gPmA+oD7gPyE/YT+iP+JAI0BkQKZA50EpQWpBrEHuQjBCckK1QvdDOkN9Q8BEA0RHRIpEzkUSRVVFmkXeRiJGZ0arRvBHNUd7R8BIBUhLSJFI10kdSWNJqUnwSjdKfUrESwxLU0uaS+JMKkxyTLpNAk1KTZNN3E4lTm5Ot08AT0lPk0/dUCdQcVC7UQZRUFGbUeZSMVJ8UsdTE1NfU6pT9lRCVI9U21UoVXVVwlYPVlxWqVb3V0RXklfgWC9YfVjLWRpZaVm4WgdaVlqmWvVbRVuVW+VcNVyGXNZdJ114XcleGl5sXr1fD19hX7NgBWBXYKpg/GFPYaJh9WJJYpxi8GNDY5dj62RAZJRk6WU9ZZJl52Y9ZpJm6Gc9Z5Nn6Wg/aJZo7GlDaZpp8WpIap9q92tPa6dr/2xXbK9tCG1gbbluEm5rbsRvHm94b9FwK3CGcOBxOnGVcfByS3KmcwFzXXO4dBR0cHTMdSh1hXXhdj52m3b4d1Z3s3gReG54zHkqeYl553pGeqV7BHtje8J8IXyBfOF9QX2hfgF+Yn7CfyN/hH/lgEeAqIEKgWuBzYIwgpKC9INXg7qEHYSAhOOFR4Wrhg6GcobXhzuHn4gEiGmIzokziZmJ/opkisqLMIuWi/yMY4zKjTGNmI3/jmaOzo82j56QBpBukNaRP5GokhGSepLjk02TtpQglIqU9JVflcmWNJaflwqXdZfgmEyYuJkkmZCZ/JpomtWbQpuvnByciZz3nWSd0p5Anq6fHZ+Ln/qgaaDYoUehtqImopajBqN2o+akVqTHpTilqaYapoum/adup+CoUqjEqTepqaocqo+rAqt1q+msXKzQrUStuK4trqGvFq+LsACwdbDqsWCx1rJLssKzOLOutCW0nLUTtYq2AbZ5tvC3aLfguFm40blKucK6O7q1uy67p7whvJu9Fb2Pvgq+hL7/v3q/9cBwwOzBZ8Hjwl/C28NYw9TEUcTOxUvFyMZGxsPHQce/yD3IvMk6ybnKOMq3yzbLtsw1zLXNNc21zjbOts83z7jQOdC60TzRvtI/0sHTRNPG1EnUy9VO1dHWVdbY11zX4Nhk2OjZbNnx2nba+9uA3AXcit0Q3ZbeHN6i3ynfr+A24L3hROHM4lPi2+Nj4+vkc+T85YTmDeaW5x/nqegy6LzpRunQ6lvq5etw6/vshu0R7ZzuKO6070DvzPBY8OXxcvH/8ozzGfOn9DT0wvVQ9d72bfb794r4Gfio+Tj5x/pX+uf7d/wH/Jj9Kf26/kv+3P9t////2wBDAAQCAwMDAgQDAwMEBAQEBQkGBQUFBQsICAYJDQsNDQ0LDAwOEBQRDg8TDwwMEhgSExUWFxcXDhEZGxkWGhQWFxb/2wBDAQQEBAUFBQoGBgoWDwwPFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhYWFhb/wAARCAAJABADASIAAhEBAxEB/8QAFwAAAwEAAAAAAAAAAAAAAAAAAwUGCP/EACcQAAEDAwMBCQAAAAAAAAAAAAECAwQABSEGBxESEyIyM0FRYYHw/8QAFQEBAQAAAAAAAAAAAAAAAAAAAwT/xAAcEQABBAMBAAAAAAAAAAAAAAABAAIDERIhQVH/2gAMAwEAAhEDEQA/AMrbC6f0/cnA6+5bZchZDUiNdgGo7KVKSEudrzjPIOMDNJ9+rBY7Fq+XHtcqKT1pKWIR62EJKEnur9TyTyPipaw+H7oN78z971S6cGAQ4jW76kxAZfq//9k=
  alt: Unsplash의 willow xk
  
  
typora-root-url: ../
---

# 1. 경험 오차 및 과적합

- 오차율(error rate): 전체 샘플($$m$$개)에서 잘못 분류한 샘플($$a$$개)의 비율, $$E = a / m$$​
- 정밀도(accuracy): 1 - 오차율, $$1 - a / m$$
- 오차(error): 예측 값과 실제 값 사이의 차이
  - 훈련 오차(training error) 또는 경험 오차(empirical error): 훈련 세트에서 발생한 오차
  - 일반화 오차(generalization error): 새로운 샘플에서 발생한 오차
    - 우리의 목표는 일반화 오차를 줄이는 것
    - 하지만 사전에 새로운 샘플에 대한 정보를 얻을 수 없기 때문에 일반화 오차를 구하는 것을 불가능
    - 따라서 일반화 오차 대신 경험 오차를 줄이는 것을 목표로 학습
- 과적합(overfitting): 모델이 훈련 데이터에 지나치게 학습된 상태
  - 경험 오차는 거의 0에 수렴
  - 일반화 오차는 매우 큼
  - 훈련 데이터의 일반적인 특징만 찾아야 하는데, 별로 중요하지 않은 특징까지 학습한 결과
  - 모델 훈련에서 넘어야 할 큰 장애물
- 과소적합(underfitting): 모델이 훈련 데이터에 특징을 잘 찾지 못한 상태
  - 경험 오차와 일반화 오차 모두 매우 큼
  - 학습을 더 진행하거나 트리의 가지를 늘리는 방법으로 해결 가능

# 2. 평가 방법

- 테스트 세트(testing set): 학습 과정에서 만나보지 못했던 새로운 샘플의 집합
  - 테스트 오차(testing error): 테스트 세트에서의 오차
    - 일반화 오차의 근삿값으로 생각
  - 테스트 오차의 정확한 계산을 위해 테스트 세트는 훈련 세트와 겹치는 샘플이 있어서는 안됨

## 데이터셋($$D$$)을 훈련 세트($$S$$)와 테스트 세트($$T$$)로 나누는 방법

### 홀드아웃(hold-out)

- 홀드아웃 방법 또는 검증 세트 기법: $$D$$를 겹치지 않는 임의의 두 집합 $$S$$와 $$T$$로 분할
  - $$D = S \cup T$$, $$S \cap T = \varnothing$$
  - 예)
    - $$D$$에 1,000개의 샘플이 있을 때 $$S$$에 700개, $$T$$에 300의 샘플로 분할
    - 만약 모델이 $$T$$에서 90개의 샘플을 잘못 분류했다면
      - 오차율은 $$E = 90 / 300 = 30\%$$
      - 정밀도는 $$1 - 30\% = 70\%$$
- 층화 추출법(stratified sampling): 샘플의 데이터 분포를 같게 나누는 방법
  - 예) 이진 분류
    - 양성 데이터와 음성 데이터가 각각 500개
    - $$S$$의 비율이 $$70\%$$, $$T$$의 비율이 $$30\%$$
    - 양성, 음성 데이터가 $$S$$에는 350개씩, $$T$$에는 150개씩 들어 있음
- 다른 방법으로는 랜덤으로 $$n$$번 분류 후 평균을 계산해 분류할 수도 있음
  - 예) 이진 분류
    - 랜덤하게 100번 분할했을 때의 $$S$$, $$T$$의 양성, 음성 데이터 개수의 평균을 계산해 최종 분할
- $$S$$와 $$T$$의 비율을 정하는 것도 매우 중요
  - $$S$$의 개수가 많을 수록 모델은 $$D$$에 가깝게 학습되지만, 테스트 결과는 불안정적
    - 분산이 크고 편향이 작음
  - $$T$$의 개수가 많을수록 $$S$$와 $$D$$의 차이가 벌어지기 때문에 모델이 편향될 수 있음
    - 편향이 크고 분산이 작음
  - 따라서 대부분 20~30%를 테스트 세트로 사용

### 교차 검증(cross validation)

- k-폴드 교차 검증(k-fold cross validation)

  ![k_fold](/assets/img/2024-04-12-machine-learning-2/k_fold.png){: w="50%" h="50%"}

  - $$D$$를 $$k$$개의 서로소 집합으로 분할
    - $$D = D_1 \cup D_2 \cup \cdots \cup D_k$$, $$D_i \cap D_j = \varnothing$$
    - 각 부분집합이 데이터 분포를 잘 반영하도록 층화 추출법을 이용해 분할
  - 아래 방법으로 $$k$$번 학습, 테스트
    - $$D_i$$를 $$T$$로, 나머지를 $$S$$로 사용

  - $$k$$에 따라 테스트 결과의 안정성이 달라짐
    - $$k$$는 주로 10, 5, 20을 사용
  - 이러한 과정을 $$p$$번 랜덤한 부분집합을 이용해 반복
    - 즉, 최종 결과는 $$p$$번의 k-fold를 실행한 값을 평균
    - 주로 10차 10-fold 교차 검증을 사용(즉 100번의 테스트를 진행)

- LOOCV(Leave-One-Out Cross Validation): $$m$$개의 샘플이 있는 $$D$$에 대하여 $$k=m$$인 k-fold를 실행

  - $$S$$가 $$D$$와 비교했을 때 1개의 샘플만 차이나기 때문에 학습된 모델이 $$D$$와 매우 비슷
    - 편향이 작음
  - 하지만 $$m$$이 클 때, 계산량이 많다는 단점이 있음

