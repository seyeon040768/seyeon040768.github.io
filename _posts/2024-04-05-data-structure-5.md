---
title: 자료구조 5. 큐
author: seyeon
date: 2024-04-05 01:00:00 +0900
categories: [Computer Science, Data Structure]
tags: [data, structure]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-04-05-data-structure-5/data_structure_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Jigar Panchal
  
typora-root-url: ../
---

# 코드

- 모든 코드는 [깃허브](https://github.com/seyeon040768/data_structure)에서 확인하실 수 있습니다.

# 큐(queue)

- 대기줄과 비슷한 형태의 자료구조
  - 데이터를 추가할 때는 맨 뒤에만 추가 가능(`enqueue`, `push`)
  - 데이터를 삭제할 때는 맨 앞에만 삭제 가능(`dequeue`, `pop`)
  - 이러한 구조를 FIFO(First In First Out)라고 부름
- queue의 기능
  - `isFull`: 큐가 포화상태인지 확인
  - `isEmpty`: 큐가 비어있는지 확인
  - `enqueue`: 큐의의 맨 뒤에 새로운 값을 추가
    - `isFull`로 포화상태가 아닌것을 확인 후 값 추가
  - `dequeue`: 큐의 맨 앞의 값을 제거하고 반환
    - `isEmpty`로 스택이 비어있지 않았다는 것을 확인 후 값 삭제
  - `peek`: 큐의 맨 앞의 값을 확인
    - `isEmpty`로 스택이 비어있지 않았다는 것을 확인 후 값 확인
- 대기열이나 버퍼에 사용

## 선형 큐(linear queue)

![queue](/assets/img/2024-04-05-data-structure-5/queue.png){: w="50%" h="50%"}

- 위 그림처럼 `front`와 `rear`를 이용해 앞과 뒤를 표시
  - 처음에는 `front`와 `rear` 모두 `-1`
  - `enqueue`를 한다면 `rear`가 `1` 증가
  - `dequeue`를 한다면 `front`가 `1` 증가
  - 대부분 `front`는 첫 원소의 이전 `index`를 나타냄
- 선형 큐의 단점
  - `Dequeue`를 하면 앞에 빈 공간이 생김
  - 뒤의 원소를 앞으로 이동시키는 방법이 있지만 오래 걸림

- c언어
  - 선형 큐 구조체 정의

    ```c
    typedef struct
    {
    	int front;
    	int rear;
    	int elements[MAX_QUEUE_SIZE];
    } Queue;
    ```

    - 구조체 초기화 시 `front`와 `rear`를 `-1`로 초기화

  - `IsFull`

    ```c
    int IsFull(const Queue* queue)
    {
    	return (queue->rear == MAX_QUEUE_SIZE - 1);
    }
    ```

  - `IsEmpty`

    ```c
    int IsEmpty(const Queue* queue)
    {
    	return (queue->front == queue->rear);
    }
    ```

  - `Enqueue`

    ```c
    void Enqueue(Queue* queue, int value)
    {
    	assert(!IsFull(queue));
    
    	queue->elements[++(queue->rear)] = value;
    }
    ```

  - `Dequeue`

    ```c
    int Dequeue(Queue* queue)
    {
    	assert(!IsEmpty(queue));
    
    	return queue->elements[++(queue->front)];
    }
    ```

  - `Peek`

    ```c
    int Peek(Queue* queue)
    {
    	assert(!IsEmpty(queue));
    
    	return queue->elements[queue->front + 1];
    }
    ```

## 원형 큐(circular queue)

![circular_queue](/assets/img/2024-04-05-data-structure-5/circular_queue.png){: w="50%" h="50%"}

- 선형 큐의 단점을 보완한 큐
- 포화상태와 공백상태를 구별하기 위해 항상 공간 하나를 비워둠
  - 처음에는 `front`와 `rear` 모두 `0`
  - 만약 `rear`가 `front`의 한칸 뒤에 있다면 포화상태
- c언어
  - 원형 큐 구조체 정의

    ```c
    typedef struct
    {
    	int front;
    	int rear;
    	int elements[MAX_QUEUE_SIZE];
    } CircularQueue;
    ```

    - 구조체 초기화 시 `front`와 `rear`를 `-1`로 초기화

  - `IsFull`

    ```c
    int IsFull(const CircularQueue* queue)
    {
    	return (queue->front == (queue->rear + 1) % MAX_QUEUE_SIZE);
    }
    ```

  - `IsEmpty`

    ```c
    int IsEmpty(const CircularQueue* queue)
    {
    	return (queue->front == queue->rear);
    }
    ```

  - `Enqueue`

    ```c
    void Enqueue(CircularQueue* queue, int value)
    {
    	assert(!IsFull(queue));
    
    	queue->rear = (queue->rear + 1) % MAX_QUEUE_SIZE;
    	queue->elements[queue->rear] = value;
    }
    ```
  
  - `Dequeue`
  
    ```c
    int Dequeue(CircularQueue* queue)
    {
    	assert(!IsEmpty(queue));
    
    	queue->front = (queue->front + 1) % MAX_QUEUE_SIZE;
    	return queue->elements[queue->front];
    }
    ```

  - `Peek`
  
    ```c
    int Peek(CircularQueue* queue)
    {
    	assert(!IsEmpty(queue));
    
    	return queue->elements[(queue->front + 1) % MAX_QUEUE_SIZE];
    }
    ```

## 덱(deque)

- double ended queue의 줄임말
- 앞과 뒤에서 모두 삽입과 삭제가 가능
- 원형 큐를 응용해 구현
- deque의 추가적인 기능
  - `add_rear`: 맨 뒤에 원소 추가
  - `delete_rear`: 맨 뒤의 원소 제거
  - `add_front`: 맨 앞에 원소 추가
  - `delete_front`: 맨 앞의 원소 제거
  - `get_rear`: 맨 뒤의 원소 확인
  - `get_front`: 맨 앞의 원소 확인
- c언어
  - 덱 구조체 정의

    ```c
    typedef struct
    {
    	int front;
    	int rear;
    	int elements[MAX_QUEUE_SIZE];
    } Deque;
    ```

    - 구조체 초기화 시 `front`와 `rear`를 `-1`로 초기화

  - `IsFull`

    ```c
    int IsFull(const Deque* queue)
    {
    	return (queue->front == (queue->rear + 1) % MAX_QUEUE_SIZE);
    }
    ```

  - `IsEmpty`

    ```c
    int IsEmpty(const Deque* queue)
    {
    	return (queue->front == queue->rear);
    }
    ```

  - `AddRear`

    ```c
    void AddRear(Deque* queue, int value)
    {
    	assert(!IsFull(queue));
    
    	queue->rear = (queue->rear + 1) % MAX_QUEUE_SIZE;
    	queue->elements[queue->rear] = value;
    }
    ```
  
  - `DeleteRear`
  
    ```c
    int DeleteRear(Deque* queue)
    {
    	assert(!IsEmpty(queue));
    
    	int ret = queue->elements[queue->rear];
    
    	queue->rear = (queue->rear - 1) % MAX_QUEUE_SIZE;
    
    	return ret;
    }
    ```
  
  - `AddFront`
  
    ```c
    void AddFront(Deque* queue, int value)
    {
    	assert(!IsFull(queue));
    
    	queue->elements[queue->front] = value;
    	queue->front = (queue->front - 1 + MAX_QUEUE_SIZE) % MAX_QUEUE_SIZE;
    }
    ```
    
  - `DeleteFront`
  
    ```c
    int DeleteFront(Deque* queue)
    {
    	assert(!IsEmpty(queue));
    
    	queue->front = (queue->front + 1) % MAX_QUEUE_SIZE;
    	return queue->elements[queue->front];
    }
    ```
  
  - `GetRear`
  
    ```c
    int GetRear(Deque* queue)
    {
    	assert(!IsEmpty(queue));
    
    	return queue->elements[queue->rear];
    }
    ```
  
  - `GetFront`
  
    ```c
    int GetFront(Deque* queue)
    {
    	assert(!IsEmpty(queue));
    
    	return queue->elements[(queue->front + 1) % MAX_QUEUE_SIZE];
    }
    ```
  
    
