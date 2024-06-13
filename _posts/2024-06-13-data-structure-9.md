---
title: 자료구조 9. 그래프
author: seyeon
date: 2024-06-13 01:00:00 +0900
categories: [Computer Science, Data Structure]
tags: [data, structure]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-06-13-data-structure-9/data_structure_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Jigar Panchal
  
typora-root-url: ../
---

# 코드

- 모든 코드는 [깃허브](https://github.com/seyeon040768/data_structure)에서 확인하실 수 있습니다.

# 그래프

- 연결되어 있는 노드 간의 관계를 표현하는 자료구조
  - 트리도 그래프

![graph](/assets/img/2024-06-13-data-structure-9/graph.png){: w="50%" h="50%"}*그래프 $$G$$*

- 그래프 $$G$$는 $$(V, E)$$로 표시

- 정점(vertices)
  - 여러가지 특성을 가지는 객체
  - $$V(G)$$: 그래프 $$G$$의 정점 집합
  - 노드라고도 불림
  - 예) $$V(G) = \{0, 1, 2, 3\}$$
  
- 간선(edge)
  - 정점들 간의 관계 의미
  - $$E(G)$$: 그래프 $$G$$의 간선 집합
  - 링크라고도 불림
  - 예) $$E(G) = \{(0, 1), (0, 2), (0, 3), (1, 3), (2, 3)\}$$
  - 무방향 그래프

    ![graph](/assets/img/2024-06-13-data-structure-9/graph.png){: w="50%" h="50%"}

    - 간선에 방향이 없는 그래프
    - $$E(G) = \{(0, 1), (0, 2), (0, 3), (1, 3), (2, 3)\}$$처럼 $$()$$를 이용해 간선을 표기
  - 방향 그래프

    ![directional_graph](/assets/img/2024-06-13-data-structure-9/directional_graph.png){: w="50%" h="50%"}*그래프 $$G^\prime$$*

    - 간선에 방향이 있는 그래프
    - $$E(G) = \{<0, 1>, <0, 2>, <0, 3>, <1, 3>, <2, 3>\}$$처럼 $$<\text{start}, \text{end}>$$​로 간선의 방향을 표기
  
- 부분 그래프(subgraph)
  - 그래프의 일부로 이루어진 그래프
    - 정점 집합과 간선 집합의 부분 집합으로 이루어진 그래프
  - $$V(S) \subseteq V(G)$$, $$E(S) \subseteq E(G)$$​
  
- 인접 정점(adjacent vertex)
  - 하나의 정점에서 간선에 의해 연결된 정점
  - 예) 그래프 $$G$$에서 정점 $$0$$의 인접 정점: 정점 $$1$$, 정점 $$2$$, 정점 $$3$$​
  
- 그래프의 차수(degree)
  - 무방향 그래프
    - 하나의 정점에서 연결된 다른 정점의 수(인접 정점의 수)
    - 예) 그래프 $$G$$에서 정점 $$0$$​의 차수: 3
  - 방향 그래프
    - 진입 차수, 내차수(in-degree): 외부에서 오는 간선의 수
    - 진출 차수, 외차수(out-degree): 외부로 향하는 간선의 후
    - 모든 진입(진출) 차수의 합은 간선의 수
    - 예) 
      - 그래프 $$G^\prime$$에서 정점 $$3$$의 내차수: 3
      - 그래프 $$G^\prime$$에서 정점 $$0$$​의 외차수: 3
  
- 그래프의 경로(path)
  - 정점 $$s$$로부터 정점 $$e$$까지 경로: 정점의 나열 $$s, v1, v2, ..., vk, e$$
    - 단, 반드시 나열된 정점 사이에 간선이 존재해야 함
    - 예) 그래프 $$G$$에서 $$0, 1, 3$$은 경로이지만 $$0, 1, 2$$는 경로가 아님
  - 단순 경로(simple path): 경로 중에 반복되는 간선이 없는 경로
    - 예) 그래프 $$G$$에서 $$0, 1, 3, 2$$
  - 사이클(cycle): 단순 경로의 시작 정점과 종료 정점이 동일한 경로
    - 예) 그래프 $$G$$에서 $$0, 1, 3, 0$$​
  - 연결 그래프(connected graph): 모든 정점 사이에 항상 경로 존재하는 그래프
  - 완전 그래프(complete graph): 모든 정점이 연결되어 있는 그래프
    - $$n$$개의 정점을 가진 완전 그래프의 간선의 수는 $$\frac{n\times (n - 1)}{2}$$
  
- 네트워크, 가중치 그래프(weighted graph)

  ![weighted_graph](/assets/img/2024-06-13-data-structure-9/weighted_graph.png){: w="50%" h="50%"}

  - 간선에 비용(cost)이나 가중치(weight)가 할당된 그래프
  - 예) 도시 사이의 거리
  
- 그래프의 기능
  - `create`: 그래프 생성
  - `is_empty`: 그래프가 비었는지 확인
  - `is_full`: 그래프가 포화 상태인지 확인
  - `insert_vertex`: 그래프에 정점을 추가
  - `delete_vertex`: 그래프에 정점을 삭제
  - `insert_edge`: 그래프에 간선을 추가
  - `delete_edge`: 그래프에 간선을 삭제
  - `adjacent`: 정점의 인접 정점을 반환
  
- 그래프 표현법
  - 인접 행렬 방법
  - 인접 리스트 방법


## 그래프 표현법

### 인접 행렬(adjacent matrix) 방법

![adjacent_matrix](/assets/img/2024-06-13-data-structure-9/adjacent_matrix.png)

- 간선을 행렬로 표현하는 방법
- 간선 $$(i, j)$$가 존재하면 $$\mathbf{M}_{ij} = 1$$
- 간선 $$(i, j)$$가 존재하지 않으면 $$\mathbf{M}_{ij} = 0$$​
- c언어

  - 그래프 구조체

    ```c
    typedef struct
    {
    	int n;
    	int adjMat[MAX_VERTICES][MAX_VERTICES];
    } Graph;
    ```

  - `IsEmpty`

    ```c
    int IsEmpty(Graph* graph)
    {
    	return graph->size == 0;
    }
    ```

  - `IsFull`

    ```c
    int IsFull(Graph* graph)
    {
    	return graph->size == MAX_VERTICES;
    }
    ```

  - `Create`

    ```c
    Graph* Create()
    {
    	Graph* graph = (Graph*)malloc(sizeof(Graph));
    	if (graph == NULL)
    	{
    		exit(1);
    	}
    
    	graph->n = 0;
    	
    	for (int r = 0; r < MAX_VERTICES; ++r)
    	{
    		for (int c = 0; c < MAX_VERTICES; ++c)
    		{
    			graph->adjMat[r][c] = 0;
    		}
    	}
    }
    ```

  - `InsertVertex`

    ``` c
    void InsertVertex(Graph* graph)
    {
    	if (IsFull(graph))
    	{
    		return;
    	}
    
    	++(graph->size);
    }
    
    ```

  - `DeleteVertex`

    ```c
    void DeleteVertex(Graph* graph, int vertex)
    {
    	if ((vertex < 0) || (vertex >= graph->size))
    	{
    		return;
    	}
    
    	for (int r = vertex + 1; r < graph->size; ++r)
    	{
    		for (int c = 0; c < vertex; ++c)
    		{
    			graph->adjMat[r - 1][c] = graph->adjMat[r][c];
    		}
    	}
    
    	for (int c = vertex + 1; c < graph->size; ++c)
    	{
    		for (int r = 0; r < vertex; ++r)
    		{
    			graph->adjMat[r][c - 1] = graph->adjMat[r][c];
    		}
    	}
    
    	for (int r = vertex + 1; r < graph->size; ++r)
    	{
    		for (int c = vertex + 1; c < graph->size; ++c)
    		{
    			graph->adjMat[r - 1][c - 1] = graph->adjMat[r][c];
    		}
    	}
    
    	--(graph->size);
    }
    ```

  - `InsertEdge`

    ```c
    void InsertEdge(Graph* graph, int start, int end)
    {
    	if ((start < 0) || (start >= graph->size) || (end < 0) || (end >= graph->size))
    	{
    		return;
    	}
    
    	graph->adjMat[start][end] = 1;
    	graph->adjMat[end][start] = 1;
    }
    ```

  - `DeleteEdge`

    ```c
    void DeleteEdge(Graph* graph, int start, int end)
    {
    	if ((start < 0) || (start >= graph->size) || (end < 0) || (end >= graph->size))
    	{
    		return;
    	}
    
    	graph->adjMat[start][end] = 0;
    	graph->adjMat[end][start] = 0;
    }
    ```

### 인접 리스트(adjacency list) 방법

![adjacency_list](/assets/img/2024-06-13-data-structure-9/adjacency_list.png)

- 각 정점에 인접한 정점들을 연결 리스트로 표현

# 그래프 탐색(graph traversal)

- 그래프의 한 정점에서 모든 정점을 방문하는 과정

## 깊이 우선 탐색(DFS, Depth First Search)

- 한 방향으로 갈 수 있을 때까지 가다가 가장 가까운 갈림길로 돌아와서 다른 방향을 탐색하는 방법
- 스택을 이용하여 구현

![dfs](/assets/img/2024-06-13-data-structure-9/dfs.png)

1. 정점 $$0$$에서 탐색 시작
2. 정점 $$1$$​에서 탐색 시작
3. 정점 $$3$$에서 탐색 시작
4. 갈 수 있는 곳이 없어 정점 $$1$$에서 다시 탐색 시작
5. 갈 수 있는 곳이 없어 정점 $$0$$에서 다시 탐색 시작
6. 정점 $$2$$에서 탐색 시작
7. 갈 수 있는 곳이 없어 정점 $$0$$에서 다시 탐색 시작
8. 갈 수 있는 곳이 없어 탐색 종료

- 시간복잡도: $$O(n^2)$$
  - 인접 리스트의 경우 $$O(n + e)$$($$e$$는 간선의 수)

- c언어

  ```c
  void DFS(Graph* graph, int startVertex)
  {
  	static int visited[MAX_VERTICES] = { 0, };
  
  	visited[startVertex] = 1;
  	printf("%d -> ", startVertex);
  
  	for (int i = 0; i < graph->size; ++i)
  	{
  		if (graph->adjMat[startVertex][i] && !visited[i])
  		{
  			DFS(graph, i);
  		}
  	}
  }
  ```

## 넓이 우선 탐색(BFS, Breadth First Search)

- 시작 정점으로부터 가까운 정점을 먼저 방문하고 멀리 떨어져 있는 정점을 나중에 탐색하는 방법
- 큐를 이용하여 구현

![bfs](/assets/img/2024-06-13-data-structure-9/bfs.png)

1. 정점 $$3$$에서 탐색 시작, 정점 $$0$$과 $$1$$ 탐색 가능
2. 정점 $$0$$에서 탐색 시작, 정점 $$2$$ 탐색 가능
3. 정점 $$1$$에서 탐색 시작, 탐색 가능한 정점 없음
4. 정점 $$2$$에서 탐색 시작, 탐색 가능한 정점 없음, 탐색 종료

- 시간복잡도: $$O(n^2)$$

  - 인접 리스트의 경우 $$O(n + e)$$($$e$$는 간선의 수)

- c언어

  ```c
  void BFS(Graph* graph, int startVertex)
  {
  	static int visited[MAX_QUEUE_SIZE] = { 0, };
  	Queue queue = { .front = 0, .rear = 0 };
  
  	visited[startVertex] = 1;
  	Enqueue(&queue, startVertex);
  
  	while (!IsEmptyQueue(&queue))
  	{
  		int vertex = Dequeue(&queue);
  		printf("%d -> ", vertex);
  
  		for (int i = 0; i < graph->size; ++i)
  		{
  			if (graph->adjMat[vertex][i] && !visited[i])
  			{
  				visited[i] = 1;
  				Enqueue(&queue, i);
  			}
  		}
  	}
  }
  ```
