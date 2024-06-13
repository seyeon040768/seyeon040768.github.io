---
title: 자료구조 10. 정렬
author: seyeon
date: 2024-06-13 01:00:00 +0900
categories: [Computer Science, Data Structure]
tags: [data, structure]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-06-13-data-structure-10/data_structure_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Jigar Panchal
  
typora-root-url: ../
---

# 코드

- 모든 코드는 [깃허브](https://github.com/seyeon040768/data_structure)에서 확인하실 수 있습니다.

# 정렬

- 정보를 기준에 따라 나열하는 것
- 일반적으로 정렬시킬 대상은 레코드(recode)
  - 레코드는 필드(field)로 구성되어 있음
  - 키(key) 필드를 기준으로 레코드끼리 구별
  - 예) 학생 레코드
    - 이름 필드
    - 학번 필드(key)
    - 주소 필드
    - 연락처 필드
- 레코드의 특징에 따라 적합한 정렬 방법을 사용해야 함
  - 레코드의 수
  - key의 특징(문자, 정수, 실수 등)
- 정렬 알고리즘의 평가 기준
  - 비교 횟수
  - 이동 횟수
- 내부 정렬(internal sorting): 모든 데이터가 주기억장치에 저장된 상태에서 정렬
- 외부 정렬(external sorting): 외부기억장치에 대부분의 데이터가 있고 일부만 주기억장치에 저장된 상태에서 정렬
- 정렬 알고리즘의 안정성(stability): 동일한 key를 갖는 레코드들의 상대적인 위치가 정렬 후에도 바뀌지 않아야 함

## 선택 정렬(selection sort)

![selection_sort](/assets/img/2024-06-13-data-structure-10/selection_sort.png)

1. 첫번째부터 네번째까지 다음을 반복
   1. $$i$$번째 원소를 $$i \sim n$$​번째 원소 중 가장 작은 원소와 교체

- 비교 횟수: $$\frac{n(n - 1)}{2}$$

- 이동 횟수: $$3(n-1)$$

  - 교체 횟수가 $$n-1$$이므로 데이터 이동 횟수는 3배(temp 사용)

- 시간 복잡도: $$O(n^2)$$

- 안정성 만족 여부: x

- c언어

  ```c
  void SelectionSort(int array[], int len)
  {
  	int temp, minIndex;
  	for (int i = 0; i < len - 1; ++i)
  	{
  		minIndex = i;
  		for (int j = i + 1; j < len; ++j)
  		{
  			if (array[j] < array[minIndex])
  			{
  				minIndex = j;
  			}
  		}
  
  		temp = array[i];
  		array[i] = array[minIndex];
  		array[minIndex] = temp;
  	}
  }
  ```

## 삽입 정렬(insertion sort)

![insertion_sort](/assets/img/2024-06-13-data-structure-10/insertion_sort.png)

1. 두번째부터 마지막까지 차례로 key로 설정하고 다음을 반복
   1. key 이전의 원소들과 비교하여 key를 적절한 위치로 이동

- 비교 횟수

  - 최선의 경우: $$n-1$$
  - 최악의 경우: $$\frac{n(n-1)}{2}$$

- 이동 횟수

  - 최선의 경우: $$2(n-1)$$​
    - `key`로 이동, `array[j + 1]`로 이동
  - 최악의 경우: $$\frac{n(n-1)}{2} + 2(n-1)$$

- 시간 복잡도: $$O(n^2)$$

- 안정성 만족 여부: o

- c언어

  ```c
  void InsertionSort(int array[], int len)
  {
  	int i, j, key;
  
  	for (i = 1; i < len; ++i)
  	{
  		key = array[i];
  		for (j = i - 1; j >= 0; --j)
  		{
  			if (array[j] > key)
  			{
  				array[j + 1] = array[j];
  			}
  			else
  			{
  				break;
  			}
  		}
  		array[j + 1] = key;
  	}
  }
  ```

## 버블 정렬(bubble sort)

![bubble_sort](/assets/img/2024-06-13-data-structure-10/bubble_sort.png)

1. $$n - 1$$번째부터 두번째까지 다음을 반복
   1. 첫번째부터 $$i$$번째까지 다음을 반복
      1. $$j$$번째와 $$j + 1$$번째 요소를 비교하여 $$j$$번째 요소가 더 크다면 서로 교체

- 비교 횟수: $$\frac{n(n-1)}{2}$$

- 이동 횟수

  - 최선의 경우: $$0$$
  - 최악의 경우: $$3\frac{n(n-1)}{2}$$

- 시간 복잡도: $$O(n^2)$$​

- 안정성 만족 여부: o

- c언어

  ```c
  void BubbleSort(int array[], int len)
  {
  	int temp;
  	for (int i = len - 1; i > 0; --i)
  	{
  		for (int j = 0; j < i; ++j)
  		{
  			if (array[j] > array[j + 1])
  			{
  				temp = array[j];
  				array[j] = array[j + 1];
  				array[j + 1] = temp;
  			}
  		}
  	}
  }
  ```

## 합병 정렬(merge sort)

![merge_sort](/assets/img/2024-06-13-data-structure-10/merge_sort.png){: w="70%" h="70%"}

1. 배열을 두 개의 균등한 크기로 분할하여 부분 배열을 정렬
2. 정렬된 두 개의 부분 배열을 합하여 전체 배열을 정렬

- 비교 횟수: $$n\log n$$

- 이동 횟수: $$2n\log n$$

- 시간 복잡도: $$O(n\log n)$$

- 안정성 만족 여부: o

- c언어

  ```c
  void MergeRecursive(int array[], int temp[], int left, int right)
  {
  	if (left == right)
  	{
  		return;
  	}
  	int mid = (left + right) / 2;
  	int i, j, k;
  
  	MergeRecursive(array, temp, left, mid);
  	MergeRecursive(array, temp, mid + 1, right);
  
  	i = left;
  	j = mid + 1;
  	k = left;
  	while (i <= mid && j <= right)
  	{
  		if (array[i] <= array[j])
  		{
  			temp[k++] = array[i++];
  		}
  		else
  		{
  			temp[k++] = array[j++];
  		}
  	}
  
  	while (i <= mid)
  	{
  		temp[k++] = array[i++];
  	}
  
  	while (j <= right)
  	{
  		temp[k++] = array[j++];
  	}
  
  	for (i = left; i <= right; ++i)
  	{
  		array[i] = temp[i];
  	}
  }
  
  void MergeSort(int array[], int left, int right)
  {
  	int* temp = (int*)malloc(sizeof(int) * (right - left + 1));
  
  	MergeRecursive(array, temp, left, right);
  
  	free(temp);
  }
  ```

## 퀵 정렬(quick sort)

![quick_sort](/assets/img/2024-06-13-data-structure-10/quick_sort.png)

1. pivot을 기준으로 왼쪽은 pivot보다 큰 값, 오른쪽은 pivot보다 작은 값을 탐색
2. 찾은 두 값을 교환
3. `low`와 `high`가 엇갈리기 전까지 1번으로 돌아가 반복
4. `high`와 `pivot`을 교체
5. 부분 배열에 대해 재귀적으로 반복

- 비교 횟수: $$n\log n$$

- 시간 복잡도: $$O(n \log n)$$

- 안정성 만족 여부: o

- c언어

  ```c
  void QuickSort(int array[], int left, int right)
  {
      if (left >= right)
      {
          return;
      }
  
      int pivot = array[left];
      int low = left + 1;
      int high = right;
      int temp;
  
      while (low <= high)
      {
          while (low <= high && array[low] <= pivot)
          {
              ++low;
          }
  
          while (low <= high && array[high] >= pivot)
          {
              --high;
          }
  
          if (low < high)
          {
              temp = array[low];
              array[low] = array[high];
              array[high] = temp;
          }
      }
  
      array[left] = array[high];
      array[high] = pivot;
  
      QuickSort(array, left, high - 1);
      QuickSort(array, high + 1, right);
  }
  ```

  
