---
title: 자료구조 8. 우선순위 큐
author: seyeon
date: 2024-06-13 01:00:00 +0900
categories: [Computer Science, Data Structure]
tags: [data, structure]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-06-13-data-structure-8/data_structure_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Jigar Panchal
  
typora-root-url: ../
---

# 코드

- 모든 코드는 [깃허브](https://github.com/seyeon040768/data_structure)에서 확인하실 수 있습니다.

# 우선순위 큐(priority queue)
- 우선순위를 가진 항목들을 저장하는 큐

- FIFO가 아닌 우선순위가 높은 데이터가 먼저 나감

- 우선순위 큐의 기능
  - `create`: 우선순위 큐 생성
  - `is_empty`: 우선순위 큐가 비어있는지 검사
  - `is_full`: 우선순위 큐가 포화 상태인지 검사
  - `insert`: 우선순위 큐에 요소 추가
  - `delete`: 우선순위 큐에서 우선순위가 가장 높은 요소 삭제하고 반환
  - `find`: 우선순위가 가장 높은 요소 반환

- 우선순위 큐 표현법
  - 배열 표현법
  - 연결리스트 표현법
  - 힙(heap) 표현법

- 우선순위 큐가 사용되는 곳

  - 머신 스케줄링(LPT, Longest Processing Time first)

    - $$n$$개의 작업과 $$m$$​개의 스레드가 있을 때 작업을 스레드에 분배하는 방법

    ![LPT](/assets/img/2024-06-13-data-structure-8/LPT.png)

    1. 우선순위 큐(시간이 긴 작업이 우선)에 모든 작업을 차례로 삽입
    2. 다음 과정을 우선순위 큐의 원소가 없을 때까지 실행
       1. $$1$$번 스레드부터 $$m$$​번 스레드까지 차례로 우선순위 큐에서 작업을 배정
       2. $$m$$번 스레드부터 $$1$$번 스레드까지 차례로 우선순위 큐에서 작업을 배정


## 우선순위 큐 표현법

### 배열 표현법

- 순서 없는 배열 표현법
  - `insert` 할 때, 단순히 배열에 요소를 저장
  - `delete` 할 때, 우선순위가 가장 높은 요소를 찾아 반환
  - 시간 복잡도
    - `insert`: $$O(1)$$
    - `delete`: $$O(n)$$
- 정렬된 배열 표현법
  - `insert` 할 때, 요소를 정렬하여 저장
  - `delete` 할 때, 맨 앞 원소 반환
  - 시간 복잡도
    - `insert`: $$O(n)$$
    - `delete`: $$O(1)$$

## 연결리스트 표현법

- 순서 없는 연결리스트 표현법
  - `insert` 할 때, 단순히 연결리스트에 요소를 저장
  - `delete` 할 때, 우선순위가 가장 높은 요소를 찾아 반환
  - 시간 복잡도
    - `insert`: $$O(1)$$
    - `delete`: $$O(n)$$
- 정렬된 연결리스트 표현법
  - `insert` 할 때, 요소를 정렬하여 저장
  - `delete` 할 때, 맨 앞 원소 반환
  - 시간 복잡도
    - `insert`: $$O(n)$$
    - `delete`: $$O(1)$$

### 힙 표현법

- 힙: 완전 이진 트리의 한 종류
  - 최대 힙(max heap): 부모 노드의 값이 자식 노드의 값보다 크거나 같은 완전 이진 트리

  - 최소 힙(min heap): 부모 노드의 값이 자식 노드의 값보다 작거자 같은 완전 이진 트리

  - 힙은 완전 이진 트리이므로 배열을 이용해 구현

    - 각 노드의 번호를 배열의 인덱스로 생각

    - 왼쪽 자식의 인덱스: `[부모의 인덱스] * 2`

    - 오른쪽 자식의 인덱스: `[부모의 인덱스] * 2 + 1`

    - 부모의 인덱스: `[자식의 인덱스] / 2`

    - c언어

      ```c
      typedef struct
      {
      	int heap[MAX_HEAP_SIZE];
      	int heapSize;
      } Heap;
      ```

  - 힙의 삽입 연산

    ![heap_insert](/assets/img/2024-06-13-data-structure-8/heap_insert.png)

    1. 마지막 노드에 이어서 새로운 노드 삽입
    2. 부모 노드들과 교환하며 적절한 위치로 이동

    - c언어

      ```c
      void Insert(Heap* heap, int key)
      {
      	if (IsFull(heap))
      	{
      		return;
      	}
      
      	int i = ++(heap->heapSize);
      
      	while ((i != 1) && (key > heap->heap[i / 2]))
      	{
      		heap->heap[i] = heap->heap[i / 2];
      		i /= 2;
      	}
      
      	heap->heap[i] = key;
      }
      ```

  - 힙의 삭제 연산

    ![heap_delete](/assets/img/2024-06-13-data-structure-8/heap_delete.png)

    1. 루트 노드 삭제
    2. 마지막 노드를 루트 노드로 이동
    3. 자식 노드 중 더 큰 노드와 교환하며 적절한 위치로 이동

    - c언어

      ```c
      int Delete(Heap* heap)
      {
      	if (IsEmpty(heap))
      	{
      		return -1;
      	}
      
      	int ret = heap->heap[1];
      	int last = heap->heap[(heap->heapSize)--];
      	int i = 1;
      	int next = i * 2;
      
      	while (next <= heap->heapSize)
      	{
      		if ((next < heap->heapSize) && (heap->heap[next] < heap->heap[next + 1]))
      		{
      			++next;
      		}
      
      		if (last >= heap->heap[next])
      		{
      			break;
      		}
      
      		heap->heap[i] = heap->heap[next];
      		i = next;
      		next = i * 2;
      	}
      
      	heap->heap[i] = last;
      
      	return ret;
      }
      ```

  - 시간복잡도
    - 삽입 연산: $$O(\log n)$$​
    - 삭제 연산: $$O(\log n)$$

# 힙 정렬(heap sort)

1. 정렬할 $$n$$개의 요소를 힙에 삽입
2. 하나씩 삭제하며 저장

- 힙을 이용한 정렬

- 시간복잡도: $$O(n\log n)$$

  - 요소의 개수가 $$n$$개이고 하나를 삽입하거나 삭제할 때 $$O(\log n)$$이 걸리므로 $$O(n \log n)$$

- 힙 정렬이 유용한 경우

  - 전체 자료가 아닌 큰 값 몇 개만 필요한 경우

- c언어

  ```c
  // 내림 차순 정렬
  void HeapSort(int array[], int n)
  {
  	Heap* heap = Create();
  
  	for (int i = 0; i < n; ++i)
  	{
  		Insert(heap, array[i]);
  	}
  
  	for (int i = 0; i < n; ++i)
  	{
  		array[i] = Delete(heap);
  	}
  
  	free(heap);
  }
  ```

  