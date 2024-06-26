---
title: 자료구조 6. 연결 리스트
author: seyeon
date: 2024-04-09 01:00:00 +0900
categories: [Computer Science, Data Structure]
tags: [data, structure]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-04-09-data-structure-6/data_structure_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Jigar Panchal
  
typora-root-url: ../
---

# 코드

- 모든 코드는 [깃허브](https://github.com/seyeon040768/data_structure)에서 확인하실 수 있습니다.

# 리스트(list)
- 순서가 있는 객체들의 모임
  - 원하는 위치에 요소 추가(`insert`) 및 삭제(`delete`) 가능
- list의 기능
  - `is_full`: 리스트가 포화 상태인지 확인
  - `is_empty`: 리스트가 비었는지 확인
  - `insert`: 특정 위치에 요소를 추가
  - `delete`: 특정 위치에 있는 요소를 제거
  - `clear`: 모든 요소를 제거
  - `get_value`: 특정 위치에 있는 값을 확인
  - `get_length`: 리스트의 길이를 반환
- c언어
  - 리스트 구조체 정의

    ```c
    typedef struct
    {
    	int elements[MAX_LIST_SIZE];
    	int size;
    } List;
    ```

  - `IsFull`

    ```c
    int IsFull(const List* list)
    {
    	return list->size == MAX_LIST_SIZE;
    }
    ```

  - `IsEmpty`

    ```c
    int IsEmpty(const List* list)
    {
    	return list->size == 0;
    }
    ```

  - `Insert`

    ```c
    void Insert(List* list, int pos, int value)
    {
    	assert(!IsFull(list));
    	assert(pos <= list->size);
    
    	if (pos < 0)
    	{
    		pos = list->size;
    	}
    
    	for (int i = list->size; i > pos; --i)
    	{
    		list->elements[i] = list->elements[i - 1];
    	}
    
    	list->elements[pos] = value;
    	++(list->size);
    }
    ```

  - `Delete`

    ```c
    void Delete(List* list, int pos)
    {
    	if (pos < 0)
    	{
    		pos = list->size - 1;
    	}
    
    	if (pos >= list->size || pos < 0)
    	{
    		return;
    	}
    
    	for (int i = pos; i < list->size - 1; ++i)
    	{
    		list->elements[i] = list->elements[i + 1];
    	}
    
    	--(list->size);
    }
    ```

    - 앞으로 당길 때, 마지막 쓰레기 값을 제거하지 않았음
    - `size`를 감소시켰기 때문에 제거하지 않아도 상관 없음

  - `Clear`

    ```c
    void Clear(List* list)
    {
    	list->size = 0;
    }
    ```

    - 값을 제거하는 대신 `size`를 `0`으로 설정

  - `GetValue`

    ```c
    int GetValue(const List* list, int pos)
    {
    	if (pos < 0)
    	{
    		pos = list->size - 1;
    	}
    
    	assert(pos >= 0 && pos < list->size);
    
    	return list->elements[pos];
    }
    ```

  - `GetLength`

    ```c
    int GetLength(const List* list)
    {
    	return list->size;
    }
    ```


# 연결 리스트(linked list)

![nodes](/assets/img/2024-04-09-data-structure-6/nodes.png)

- 노드(node): 연결 리스트의 기본 단위
  - 데이터 필드(data field): 실질적인 값을 저장
  - 링크 필드(link field): 다음 노드의 주소를 저장
- 연결 리스트의 기능
  - `is_empty`: 연결 리스트가 비었는지 확인
  - `get_node`: 특정 위치에 있는 노드를 확인
  - `insert`: 특정 위치에 요소를 추가
  - `delete`: 특정 위치에 있는 요소를 제거
  - `clear`: 모든 요소를 제거
  - `get_length`: 연결 리스트의 길이를 반환
  - `reverse`: 연결 리스트의 순서를 반전
- 연결 리스트의 장단점
  - 장점
    - 삽입, 삭제가 용이
    - 연속된 메모리 공간이 필요 없음
    - 메모리 공간만 충분하다면 크기 제한이 없음(유동적인 크기)
  - 단점
    - 구현이 어려움
    - 메모리 파편화

## 단순 연결 리스트(singly linked list)

![singly_linked_list](/assets/img/2024-04-09-data-structure-6/singly_linked_list.png)

- 하나의 링크 필드를 이용해 연결
- `head`가 첫 노드를 가리킴
- 마지막 노드의 링크는 `NULL`
- c언어
  - 노드&단순 연결 리스트 구조체 정의
  
    ```c
    typedef struct Node
    {
    	int data;
    	struct Node* link;
    } Node;
    
    typedef struct
    {
    	Node* head;
    	int length;
    } SinglyLinkedList;
    ```
  
  
  - `IsEmpty`
  
    ```c
    int IsEmpty(const SinglyLinkedList* list)
    {
    	return list->head == NULL;
    }
    ```
  
  - `GetNode`
  
    ```c
    Node* GetNode(const SinglyLinkedList* list, const int pos)
    {
    	if (pos < 0 || pos >= list->length)
    	{
    		return NULL;
    	}
    
    	Node* search = list->head;
    
    	for (int i = 0; i < pos; ++i)
    	{
    		search = search->link;
    	}
    
    	return search;
    }
    ```
  
  - `Insert`
  
    ```c
    int Insert(SinglyLinkedList* list, const int pos, const int data)
    {
    	Node* newNode = (Node*)malloc(sizeof(Node));
    	if (newNode == NULL)
    	{
    		return 0;
    	}
    	newNode->data = data;
    
    	if (pos == 0)
    	{
    		newNode->link = list->head;
    		list->head = newNode;
    
    		++(list->length);
    		return 1;
    	}
    
    	Node* prev;
    	if ((prev = GetNode(list, pos - 1)) == NULL) // if pos is wrong
    	{
    		free(newNode);
    		return 0;
    	}
    
    	newNode->link = prev->link;
    	prev->link = newNode;
    	
    	++(list->length);
    	return 1;
    }
    ```
  
  - `Delete`
  
    ```c
    void Delete(SinglyLinkedList* list, const int pos)
    {
    	if (pos == 0)
    	{
    		Node* current = list->head;
    		list->head = current->link;
    		free(current);
    
    		--(list->length);
    		return;
    	}
    
    	Node* prev = GetNode(list, pos - 1);
    	if (prev == NULL || prev->link == NULL) // if pos is wrong
    	{
    		return;
    	}
    
    	Node* current = prev->link;
    	prev->link = current->link;
    	free(current);
    
    	--(list->length);
    }
    ```
  
  - `Clear`
  
    ```c
    void Clear(SinglyLinkedList* list)
    {
    	Node* search = list->head;
    	Node* temp;
    
    	while (search != NULL)
    	{
    		temp = search->link;
    		free(search);
    		search = temp;
    	}
    
    	list->head = NULL;
    	list->length = 0;
    }
    ```
  
  - `GetLength`
  
    ```c
    int GetLength(const SinglyLinkedList* list)
    {
    	return list->length;
    }
    ```
  
  - `Reverse`
  
    ```c
    void Reverse(SinglyLinkedList* list)
    {
    	Node* current = list->head;
    	Node* prev = NULL;
    	Node* next;
    
    	while (current != NULL)
    	{
    		next = current->link;
    		current->link = prev;
    		prev = current;
    		current = next;
    	}
    
    	list->head = prev;
    }
    ```

## 원형 연결 리스트(circular linked list)

![circular_linked_list](/assets/img/2024-04-09-data-structure-6/circular_linked_list.png)

- 마지막 노드의 링크가 첫 번째 노드를 가리키는 연결 리스트
- 장점
  - 한 노드에서 모든 노드로의 접근이 가능
  - `head`가 마지막 노드를 가리키도록 설정하면 처음과 마지막에 노드를 삽입하기 편함
- c언어
  - 노드&단순 연결 리스트 구조체 정의
  
    ```c
    typedef struct Node
    {
    	int data;
    	struct Node* link;
    } Node;
    
    typedef struct
    {
    	Node* head;
    	int length;
    } CircularLinkedList;
    ```
  
  
  - `IsEmpty`
  
    ```c
    int IsEmpty(const CircularLinkedList* list)
    {
    	return list->head == NULL;
    }
    ```
  
  - `GetNode`
  
    ```c
    Node* GetNode(const CircularLinkedList* list, const int pos)
    {
    	if (pos < 0 || pos >= list->length || IsEmpty(list))
    	{
    		return NULL;
    	}
    
    	Node* search = list->head->link;
    
    	for (int i = 0; i < pos; ++i)
    	{
    		search = search->link;
    	}
    
    	return search;
    }
    ```
  
  - `Insert`
  
    ```c
    int Insert(CircularLinkedList* list, const int pos, const int data)
    {
    	Node* newNode = (Node*)malloc(sizeof(Node));
    	if (newNode == NULL)
    	{
    		return 0;
    	}
    	newNode->data = data;
    
    	Node* prev = GetNode(list, pos - 1);
    
    	if (pos == 0)
    	{
    		if (IsEmpty(list))
    		{
    			newNode->link = newNode;
    			list->head = newNode;
    
    			++(list->length);
    			return 1;
    		}
    		
    		prev = list->head;
    	}
    	else if (pos == list->length)
    	{
    		list->head = newNode;
    	}
    
    	if (prev == NULL)
    	{
    		free(newNode);
    		return 0;
    	}
    
    	newNode->link = prev->link;
    	prev->link = newNode;
    
    	++(list->length);
    	return 1;
    }
    ```
  
  - `Delete`
  
    ```c
    void Delete(CircularLinkedList* list, const int pos)
    {
    	Node* prev = GetNode(list, pos - 1);
    
    	if (pos == 0)
    	{
    		if (list->length == 1)
    		{
    			free(list->head);
    			list->head = NULL;
    
    			--(list->length);
    			return;
    		}
    		prev = list->head;
    	}
    	else if (pos == list->length - 1)
    	{
    		list->head = prev;
    	}
    
    	if (prev == NULL || prev->link == NULL)
    	{
    		return;
    	}
    
    	Node* current = prev->link;
    	prev->link = current->link;
    	free(current);
    
    	--(list->length);
    }
    ```
  
  - `Clear`
  
    ```c
    void Clear(CircularLinkedList* list)
    {
    	if (IsEmpty(list))
    	{
    		return;
    	}
    
    	Node* search = list->head;
    	Node* temp;
    
    	do
    	{
    		temp = search->link;
    		free(search);
    		search = temp;
    	} while (search != list->head);
    
        list->head = NULL;
    	list->length = 0;
    }
    ```
  
  - `GetLength`
  
    ```c
    int GetLength(const CircularLinkedList* list)
    {
    	return list->length;
    }
    ```

## 이중 연결 리스트(doubly linked list)

![doubly_linked_list](/assets/img/2024-04-09-data-structure-6/doubly_linked_list.png)

- 하나의 노드가 선행 노드와 후속 노드에 대한 두개의 링크를 가지는 연결 리스트
- 장단점
  - 장점
    - 선행 노드를 쉽게 알 수 있음
  - 단점
    - 공간을 많이 차지
- c언어
  - 노드&단순 연결 리스트 구조체 정의
  
    ```c
    typedef struct Node
    {
    	int data;
    	struct Node* lLink;
    	struct Node* rLink;
    } Node;
    
    typedef struct
    {
    	Node* head;
    	int length;
    } DoublyLinkedList;
    ```
  
  
  - `IsEmpty`
  
    ```c
    int IsEmpty(const DoublyLinkedList* list)
    {
    	return list->head == NULL;
    }
    ```
  
  - `GetNode`
  
    ```c
    Node* GetNode(const DoublyLinkedList* list, const int pos)
    {
    	if (pos < 0 || pos >= list->length || IsEmpty(list))
    	{
    		return NULL;
    	}
    
    	Node* search = list->head;
    	for (int i = 0; i < pos; ++i)
    	{
    		search = search->rLink;
    	}
    
    	return search;
    }
    ```
    
  - `Insert`
  
    ```c
    int Insert(DoublyLinkedList* list, const int pos, const int data)
    {
    	Node* newNode = (Node*)malloc(sizeof(Node));
    	if (newNode == NULL)
    	{
    		return 0;
    	}
    	newNode->data = data;
    
    	if (pos == 0)
    	{
    		newNode->rLink = list->head;
    		if (list->head != NULL)
    		{
    			list->head->lLink = newNode;
    		}
    		list->head = newNode;
    
    		++(list->length);
    		return 1;
    	}
    
    	Node* prev;
    	if ((prev = GetNode(list, pos - 1)) == NULL)
    	{
    		free(newNode);
    		return 0;
    	}
    
    	if (prev->rLink != NULL)
    	{
    		prev->rLink->lLink = newNode;
    	}
    	newNode->rLink = prev->rLink;
    	newNode->lLink = prev;
    	prev->rLink = newNode;
    
    	++(list->length);
    	return 1;
    }
    ```
    
  - `Delete`
  
    ```c
    void Delete(DoublyLinkedList* list, const int pos)
    {
    	if (pos == 0)
    	{
    		Node* current = list->head;
    		list->head = current->rLink;
    		if (list->head != NULL)
    		{
    			list->head->lLink = NULL;
    		}
    		free(current);
    
    		--(list->length);
    		return;
    	}
    
    	Node* prev = GetNode(list, pos - 1);
    	if (prev == NULL || prev->rLink == NULL)
    	{
    		return;
    	}
    
    	Node* current = prev->rLink;
    	prev->rLink = current->rLink;
    	current->rLink->lLink = prev;
    	free(current);
    
    	--(list->length);
    }
    ```
    
  - `Clear`
  
    ```c
    void Clear(DoublyLinkedList* list)
    {
    	Node* search = list->head;
    	Node* temp;
    
    	while (search != NULL)
    	{
    		temp = search->rLink;
    		free(search);
    		search = temp;
    	}
    
    	list->head = NULL;
    	list->length = 0;
    }
    ```
    
  - `GetLength`
  
    ```c
    int GetLength(const DoublyLinkedList* list)
    {
    	return list->length;
    }
    ```