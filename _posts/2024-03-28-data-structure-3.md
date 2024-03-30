---
title: 자료구조 3. 배열
author: seyeon
date: 2024-03-28 01:00:00 +0900
categories: [Computer Science, Data Structure]
tags: [data, structure]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/2024-03-28-data-structure-3/data_structure_main.jpg
  lqip: data:image/jpeg;base64,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
  alt: Unsplash의 Jigar Panchal
  
typora-root-url: ../
---

# 코드

- 모든 코드는 [깃허브](https://github.com/seyeon040768/data_structure)에서 확인하실 수 있습니다.

# 배열(array)

![array](/assets/img/2024-03-28-data-structure-3/array.png)

- 데이터를 연속적으로 저장하는 자료구조
- `index`에 `value`이 대응됨
  - `index`는 `0`부터 시작
    - 첫 번째 요소의 시작점과 배열의 시작점이 같기 때문
    - 배열의 주소 = 첫 번째 요소의 주소 + 0
  - `arr[3]`처럼 `index`를 통해 `value`에 접근할 수 있음
- c언어
  - `type arrayName[length] = { init };`


## 2차원, 3차원 배열

- 2차원 배열

  ![2d_array](/assets/img/2024-03-28-data-structure-3/2d_array.png)

- 3차원 배열

  ![3d_array](/assets/img/2024-03-28-data-structure-3/3d_array.png)

- c언어

  - 2d array: `type arrayName[row][col] = { {}, {}, ... };`

  - 3d array: `type arrayName[depth][row][col] = { { {}, {}, ...}, { {}, {}, ...}, ... };`

- 메모리에는 1차원 배열처럼 일렬로 저장됨

  - 주로 row-major 방향으로 저장
    - `[i][j]` = `i * col(width) + j`


# 구조체

- 다양한 자료형을 모아놓은 구조

- 관리의 용이성을 위해 사용

- 예)

  - 좌표를 표현하는 구조체: (x, y, z)
  - 이름과 학번을 저장하는 구조체: (name, id)

- c언어

  - 정의

    ```c
    struct StructName
    {
        type name;
        ...
    };
    ```

    - `typedef`과 함께 이용하면 편리

      ```c
      typedef struct 
      {
          type name;
          ...
      } StructName;
      ```

  - 구조체 선언

    - `struct StructName varName = { init };`
    - `typedef`를 사용한 경우: `StructName varName = { init };`
    - `StructName varName = { .name="name", ... };`처럼 멤버 변수를 초기화할 수 있음

# 다항식(polynomial)

## 방법 1

- 모든 계수를 배열에 저장
  - 최고 차항의 계수를 0번째 `index`에 저장
  - 최고 차항의 차수를 따로 저장

- 예)
  - $$ax^2+bx+c$$: `[a, b, c]`, `degree = 2`
  - $$ax^5+bx^4+cx$$: `[a, b, 0, 0, c, 0]`, `degree = 5`

- c언어
  - 다항식 구조체 정의

    ```c
    typedef struct
    {
        int degree;
        float coef[MAX_DEGREE];
    } Polynomial;
    ```

    - `degree`: 다항식의 최고 차항의 차수
    - `coef`: 다항식 계수 배열

  - 다항식 덧셈

    ```c
    Polynomial AddPolynomial(Polynomial a, Polynomial b)
    {
        // 1
        if (a.degree < b.degree)
        {
            Polynomial temp = a;
            a = b;
            b = temp;
        }
    	
        // 2
        int highestDiff = a.degree - b.degree;
        for (int i = 0; i <= b.degree; ++i)
        {
            a.coef[i + highestDiff] += b.coef[i];
        }
    
        return a;
    }
    ```

    1. `a`의 최고 차항의 차수가 `b`의 최고 차항의 차수보다 작다면 서로 swap
    2. `a`에 `b`를 덧셈
       - `b`의 최고 차항의 차수보다 차수가 큰 `a`의 항은 생각할 필요가 없음
       - 따라서 `b`를 기준으로 반복
       - `highestDiff`: `b`의 최고 차항의 계수가 `a`에서는 `a.degree - b.degree`번째이므로 `i + highestDiff`를 통해 위치 보정

  - 다항식 출력

    ```c
    void PrintPolynomial(Polynomial poly)
    {
        printf("%gx^%d", poly.coef[0], poly.degree);
        for (int i = 1; i < poly.degree; ++i)
        {
            if (poly.coef[i] == 0)
            {
                continue;
            }
            printf("%+gx^%d", poly.coef[i], poly.degree - i);
        }
        printf("%+g\n", poly.coef[poly.degree]);
    }
    ```

    - `%g`: 소수점 이하 `0` 제거
    - `%+g`: 부호 출력
    - 최고 차항의 계수는 `+`를 보여줄 필요가 없으므로 먼저 출력
    - 계수가 `0`일 경우 출력할 필요가 없으므로 반복문 내에서 검사
    - 상수항은 `x`를 출력할 필요가 없으므로 반복문 밖에서 출력

## 방법 2

- 공간을 절약하기 위해 계수가 `0`이 아닌 항만 저장
  - `(계수, 차수)` 형식의 구조체를 배열에 저장
  - `(계수, 차수)`들은 `차수`에 따른 내림차순으로 정렬되어 있다고 가정

- 예)
  - $$ax^2+bx+c$$: `{ {a, 2}, {b, 1}, {c, 0} }`
  - $$ax^5+bx^4+cx$$: `{ {a, 5}, {b, 4}, {c, 1} }`

- c언어

  - 다항식 구조체 정의

    ```c
    typedef struct
    {
    	float coef;
    	int exponent;
    } Term;
    
    typedef struct
    {
    	Term terms[MAX_TERMS];
    	int availIndex;
    } Polynomial;
    ```

    - 다항식 구조체(`Polynomial`)에서 항 구조체(`Term`) 배열을 사용
    - `availIndex`: 마지막 유효한 항의 `index`

  - 항 추가

    ```c
    int AttachTerm(Polynomial* target, Term term)
    {
        if (target->availIndex >= MAX_TERMS)
        {
            return 0;
        }
    
        target->terms[target->availIndex] = term;
        ++(target->availIndex);
    
        return 1;
    }
    ```

    - 항 개수가 최대 항 개수를 이상이면 실패(`0`) 반환
    - 마지막 항 뒤에 새로운 항 추가

  - 다항식 덧셈

    ```c
    Polynomial AddPolynomial(Polynomial a, Polynomial b)
    {
        Polynomial res = { .availIndex = 0 };
        int aIndex = 0;
        int bIndex = 0;
    
        while (aIndex < a.availIndex && bIndex < b.availIndex)
        {
            float aExpon = a.terms[aIndex].exponent;
            float bExpon = b.terms[bIndex].exponent;
    
            if (aExpon > bExpon)
            {
                AttachTerm(&res, a.terms[aIndex]);
                ++aIndex;
            }
            else if (aExpon < bExpon)
            {
                AttachTerm(&res, b.terms[bIndex]);
                ++bIndex;
            }
            else
            {
                AttachTerm(&res, (Term){ a.terms[aIndex].coef + b.terms[bIndex].coef, a.terms[aIndex].exponent });
    
                ++aIndex;
                ++bIndex;
            }
        }
    
        for (int i = aIndex; i < a.availIndex; ++i)
        {
            AttachTerm(&res, a.terms[i]);
        }
        for (int i = bIndex; i < b.availIndex; ++i)
        {
            AttachTerm(&res, b.terms[i]);
        }
    
        return res;
    }
    ```

    - `aIndex`와 `bIndex`를 이용해 처음부터 탐색, 만약 둘 중 하나라도 모든 항을 탐색하면 탐색 종료
    - `aIndex`에 해당하는 항의 차수와 `bIndex`에 해당하는 항의 차수를 비교해 더 큰 항을 결과에 추가, 만약 같다면 두 항의 계수를 더해 추가
    - 탐색을 종료하면 추가되지 못한 다항식의 항을 마저 추가

  - 다항식 출력

    ```c
    void PrintPolynomial(Polynomial poly)
    {
        printf("%gx^%d", poly.terms[0].coef, poly.terms[0].exponent);
    
        for (int i = 1; i < poly.availIndex - 1; ++i)
        {
            printf("%+gx^%d", poly.terms[i].coef, poly.terms[i].exponent);
        }
    
        if (poly.terms[poly.availIndex - 1].exponent == 0)
        {
            printf("%+g\n", poly.terms[poly.availIndex - 1].coef);
        }
        else
        {
            printf("%+gx^%d\n", poly.terms[poly.availIndex - 1].coef, poly.terms[poly.availIndex - 1].exponent);
        }
    }
    ```

    - 방법1과 유사
    - 마지막 항이 상수항일 경우 `x`를 제외하고 출력

