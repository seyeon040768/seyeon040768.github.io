---
title: 자료구조 11. 해싱
author: seyeon
date: 2024-07-07 02:00:00 +0900
categories: [Computer Science, Data Structure]
tags: [data, structure]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-07-07-data-structure-11/data_structure_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Jigar Panchal
  
typora-root-url: ../
---

# 코드

- 모든 코드는 [깃허브](https://github.com/seyeon040768/data_structure)에서 확인하실 수 있습니다.

# 해싱

- 키(key) 값을 이용해 항목을 저장하고 접근하는 자료구조
- 해시 함수: 키 값을 해시 주소로 변경하는 함수
- 해시 테이블(hash table): 해시 함수의 결과에 의해 접근이 가능한 구조
  - 딕셔너리(dictionary) 또는 맵(map)으로 불리기도 함
  - 슬롯(slot): 값을 저장할 수 있는 공간
  - 버켓(bucket): 각각의 해시 주소에 해당하는 값을 저장할 공간
    - 슬롯의 집합

## 해싱의 문제점

- 충돌(collision): 서로 다른 키에 대해 같은 해시 주소가 나오는 문제
- 오버플로우(overflow): 충돌이 버켓에 할당된 슬롯의 수보다 많이 발생하는 것
  - 반드시 오버플로우를 해결할 방법이 필요
- 좋은 해시 함수라면 **충돌이 적고** **해시 주소가 고르게 분포**되어야 하며 **계산이 빨라**야 함

## 해시 함수

- division method
  - key를 테이블의 크기로 나눈 나머지를 주소로 사용
- 비트추출 함수
  - 키를 이진수로 간주하여 임의의 위이 k개의 비트를 해시 주소로 사용
- 문자열 해시 함수
  - 문자열의 문자를 다 더한 후, 테이블의 크기로 나눈 나머지를 주소로 사용

## 충돌 해결

- 선형 조사법
  - 해시 함수를 통해 생성된 주소에 이미 값이 있을 경우 다음 주소에 값을 저장하는 방법
- 체이닝
  - 각 버켓에 연결 리스트를 할당하여 값을 저장하는 방법

## 문자열 해시 함수 + 체이닝 예시

- 해시 함수

  ```c
  unsigned int HashFunction(const char* key)
  {
      unsigned long int value = 0;
  
      for (int i = 0; i < strlen(key); i++)
      {
          value += key[i];
      }
  
      return value % TABLE_SIZE;
  }
  ```

- 해시 테이블 구조체

  ```c
  typedef struct Node
  {
      char* key;
      int value;
      struct Node* next;
  } Node;
  
  typedef struct
  {
      Node** buckets;
  } HashTable;
  ```

- `Init`

  ```c
  HashTable* Init()
  {
      HashTable* table = (HashTable*)malloc(sizeof(HashTable));
      table->buckets = (Node**)malloc(TABLE_SIZE * sizeof(Node*));
      for (int i = 0; i < TABLE_SIZE; i++)
      {
          table->buckets[i] = NULL;
      }
      return table;
  }
  ```

- `Add`

  ```c
  void Add(HashTable* table, const char* key, int value)
  {
      unsigned int bucket = HashFunction(key);
      Node* newNode = (Node*)malloc(sizeof(Node));
      newNode->key = _strdup(key);
      newNode->value = value;
      newNode->next = table->buckets[bucket];
      table->buckets[bucket] = newNode;
  }
  ```

- `Search`

  ```c
  int Search(HashTable* table, const char* key)
  {
      unsigned int bucket = HashFunction(key);
      Node* node = table->buckets[bucket];
      while (node != NULL)
      {
          if (strcmp(node->key, key) == 0)
          {
              return node->value;
          }
          node = node->next;
      }
      return -1;
  }
  ```

- `Delete`

  ```c
  void Delete(HashTable* table, const char* key)
  {
      unsigned int bucket = HashFunction(key);
      Node* node = table->buckets[bucket];
      Node* prev = NULL;
  
      while (node != NULL && strcmp(node->key, key) != 0)
      {
          prev = node;
          node = node->next;
      }
  
      if (node == NULL)
      {
          return;
      }
  
      if (prev == NULL)
      {
          table->buckets[bucket] = node->next;
      }
      else
      {
          prev->next = node->next;
      }
  
      free(node->key);
      free(node);
  }
  ```

  
