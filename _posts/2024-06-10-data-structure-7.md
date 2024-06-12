---
title: 자료구조 7. 트리
author: seyeon
date: 2024-06-10 01:00:00 +0900
categories: [Computer Science, Data Structure]
tags: [data, structure]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-06-10-data-structure-7/data_structure_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Jigar Panchal
  
typora-root-url: ../
---

# 코드

- 모든 코드는 [깃허브](https://github.com/seyeon040768/data_structure)에서 확인하실 수 있습니다.

# 트리(Tree)

- 계층적인 구조를 나타내는 자료구조
- 부모-자식 관계의 노드들로 구성

![tree](/assets/img/2024-06-10-data-structure-7/tree.png){: w="50%" h="50%"}

- 노드(node): 트리의 구성 요소
- 루트 노드(root node): 부모가 없는 최상위 노드
- 레벨(level): 트리의 각 층의 번호
- 높이(height): 트리의 최대 레벨, 층의 개수
- 차수(degree): 각 노드가 가지고 있는 자식 노드의 개수

# 이진 트리(Binary Tree)

- 모든 노드가 2개 이하의 자식 노드를 가지고 있는 트리
  - 모든 노드의 차수가 2 이하
- 이진 트리의 성질
  - 노드의 개수가 $$n$$개이면 간선의 개수는 $$n-1$$
  - 높이가 $$h$$인 이진 트리의 경우, 최소 $$h$$개, 최대 $$2^h - 1$$개의 노드를 가짐
- 포화 이진 트리: 각 레벨에 노드가 모두 채워져 있는 이진 트리
  - 전체 노드 개수: $$2^h - 1$$
- 완전 이진 트리: 레벨 1부터 $$h-1$$까지는 노드가 모두 채워져 있고, 마지막 레벨에서는 왼쪽부터 오른쪽으로 노드가 순서대로 채워져 있는 이진 트리
- 이진 트리 표현법
  - 배열 표현법
  - 링크(포인터) 표현법

## 이진 트리 표현법
### 배열 표현법

![array_notation](/assets/img/2024-06-10-data-structure-7/array_notation.png){: w="50%" h="50%"}

- 이진 트리를 포화 이진 트리라고 가정하고, 각 노드에 번호를 붙여 그 번호를 배열의 인덱스로 삼아 저장하는 방법

### 링크 표현법

![link_notation](/assets/img/2024-06-10-data-structure-7/link_notation.png){: w="70%" h="70%"}

- 포인터를 이용해여 부모 노드가 자식 노드를 가리키게 하는 방법

- c언어

  ```c
  typedef struct TreeNode
  {
  	int data;
  	struct TreeNode* left;
  	struct TreeNode* right;
  } TreeNode;
  ```

## 이진 트리의 순회

- 순회: 트리의 노드들을 체계적으로 방문하는 것
- 순회 노드
  - V: 현재 노드
  - L: 왼쪽 자손 노드
  - R: 오른쪽 자손 노드
- 순회 방법
  - 전위 순회(VLR)
  - 중위 순회(LVR)
  - 후위 순회(LRV)
  - 레벨 순회

### 전위 순회(Preorder Traversal, VLR)

1. 루트 노드를 방문
2. 왼쪽 서브 트리를 방문
3. 오른쪽 서브 트리를 방문

- c언어

  ```c
  void Preorder(TreeNode* node)
  {
  	if (node == NULL)
  	{
  		return;
  	}
      
  	printf("%d\n", node->data);
  	Preorder(node->left);
  	Preorder(node->right);
  }
  ```

### 중위 순회(Inorder Traversal, LVR)

1. 왼쪽 서브 트리를 방문
2. 루트 노드를 방문
3. 오른쪽 서브 트리를 방문

- c언어

  ```c
  void Inorder(TreeNode* node)
  {
  	if (node == NULL)
  	{
  		return;
  	}
  
  	Inorder(node->left);
  	printf("%d\n", node->data);
  	Inorder(node->right);
  }
  ```

### 후위 순회(Postorder Traversal, LRV)

1. 왼쪽 서브 트리를 방문
2. 오른쪽 서브 트리를 방문
3. 루트 노드를 방문

- c언어

  ```c
  void Postorder(TreeNode* node)
  {
  	if (node == NULL)
  	{
  		return;
  	}
  
  	Postorder(node->left);
  	Postorder(node->right);
  	printf("%d\n", node->data);
  }
  ```

### 레벨 순회(Levelorder Traversal)

- 각 노드를 레벨 순으로 방문
- 재귀(스택) 대신 큐를 사용

- c언어

  ```c
  void Levelorder(TreeNode* root)
  {
  	Queue queue = { .front = -1, .rear = -1 };
  
  	Enqueue(&queue, root);
  	while (!IsEmpty(&queue))
  	{
  		TreeNode* node = Dequeue(&queue);
  		printf("%d\n", node->data);
  		if (node->left != NULL)
  		{
  			Enqueue(&queue, node->left);
  		}
  		if (node->right != NULL)
  		{
  			Enqueue(&queue, node->right);
  		}
  	}
  }
  ```

## 스레드 이진 트리

- `NULL` 링크를 이용하여 순환 없이 트리의 노드를 순회

- 중위 순회 시 `NULL` 링크에 중위 후속자(중위 순회 시 다음 노드)를 저장

- c언어

  - 스레이 이진 트리 구조체

    ```c
    typedef struct TreeNode
    {
    	int data;
    	struct TreeNode* left;
    	struct TreeNode* right;
    	int isThread;
    } TreeNode;
    ```

  - 중위 후속자 탐색 함수

    ```c
    TreeNode* FindSuccessor(TreeNode* node)
    {
    	TreeNode* ret = node->right;
    	if (ret == NULL || ret->isThread)
    	{
    		return ret;
    	}
    
    	while (ret->left != NULL)
    	{
    		ret = ret->left
    	}
    
    	return ret;
    }
    ```

  - 중위 순회

    ```c
    void Inorder(TreeNode* root)
    {
    	TreeNode* node = root;
    	
    	while (node->left != NULL)
    	{
    		node = node->left;
    	}
    
    	do
    	{
    		printf("%d\n", node->data);
    		node = FindSuccessor(node);
    	} while (node != NULL);
    }
    ```

## 이진 탐색 트리

- 탐색 작업을 효율적으로 하기 위한 이진 트리

- 왼쪽 자식 노드 < 부모 노드 < 오른쪽 자식 노드 형태

  - 중위 순회를 하면 정렬된 값을 얻을 수 있음

- 탐색 연산

  - 원하는 값과 비교한 값이 같으면 탐색 성공

  - 원하는 값보다 비교한 값이 크면 왼쪽 자식 노드를 기준으로 다시 시작

  - 원하는 값보다 비교한 값이 작으면 오른쪽 자식 노드를 기준으로 다시 시작

  - c언어

    ```c
    TreeNode* Search(TreeNode* node, int key)
    {
    	if (node == NULL)
    	{
    		return NULL;
    	}
    
    	if (node->data == key)
    	{
    		return node;
    	}
    
    	if (node->data > key)
    	{
    		Search(node->left, key);
    	}
    	else
    	{
    		Search(node->right, key);
    	}
    }
    ```

- 삽입 연산

  - 이진 탐색 트리에 원소를 삽입하기 위해서는 먼저 탐색 연산을 수행해야 함

  - 탐색을 실패한 위치에 새로운 노드를 삽입

  - c언어

    ```c
    TreeNode* Insert(TreeNode* node, int key)
    {
    	if (node == NULL)
    	{
    		return MakeNode(key);
    	}
    
    	if (node->data > key)
    	{
    		node->left = Insert(node->left, key);
    	}
    	else
    	{
    		node->right = Insert(node->right, key);
    	}
    
    	return node;
    }
    ```

- 삭제 연산

  - 삭제하려는 노드가 단말 노드(자식 노드가 없는 노드)인 경우

    - 부모 노드를 찾아 연결을 해제

  - 삭제하려는 노드가 하나의 서브 트리를 가지고 있는 경우

    - 서브 트리를 부모 노드에 연결

  - 삭제하려는 노드가 두개의 서브 트리를 가지고 있는 경우

    - 삭제하려는 노드와 가장 비슷한 값을 가진 노드를 삭제 노드의 위치로 이동
      - 가장 비슷한 값은 **왼쪽 서브 트리의 가장 큰 값** 또는 **오른쪽 서브 트리의 가장 작은 값** 중 하나
      - 두 노드 중 아무거나 하나 선택하면 됨

  - c언어

    ```c
    TreeNode* Delete(TreeNode* node, int key)
    {
    	if (node == NULL)
    	{
    		return NULL;
    	}
    
    	if (node->data > key)
    	{
    		node->left = Delete(node->left, key);
    	}
    	else if (node->data < key)
    	{
    		node->right = Delete(node->right, key);
    	}
    	else
    	{
    		if (node->left == NULL) // case 1 or 2
    		{
    			TreeNode* temp = node->right;
    			free(node);
    			return temp;
    		}
    		else if (node->right == NULL) // case 1
    		{
    			TreeNode* temp = node->left;
    			free(node);
    			return temp;
    		}
    
    		// case 3
    		TreeNode* leftMax = node->left;
    		while (leftMax->right != NULL)
    		{
    			leftMax = leftMax->right;
    		}
    
    		TreeNode* rightMin = node->right;
    		while (rightMin->left != NULL)
    		{
    			rightMin = rightMin->left;
    		}
    
    		node->data = rightMin->data;
    		node->right = Delete(node->right, rightMin->data);
    	}
    	return node;
    }
    ```

- 이진 탐색 트리의 성능
  - 탐색, 삽입, 삭제 연산의 시간 복잡도는 높이 $$h$$에 비례
    - 최선의 경우(이진 트리가 균형적으로 생성되어 있는 경우): $$h = \log_2n$$
    - 최악의 경우(한 쪽으로 치우친 경우): $$h = n$$​



