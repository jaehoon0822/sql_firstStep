# CH12 수치연산

<br />

| 연산자 | 연산 |
| :---: | :---: |
| + | 덧셈 |
| - | 뺄셈 |
| * | 곱셈 |
| / | 나누기 |
| % | 나머지 |

<br />

| 우선순위 | 연산자 |
| :---: | :---: |
| 1 | * / % |
| 2 | + - |

<br />

> ***" sql 명령에는 여러 부분에서 산술 연산자를 사용해 연산할 수 있습니다. "***
>

<br />

## select 구로 연산.

<br />

```sql

select 식, 식... from talbe;

```

<br />

## 열의 별명.

<br />

```sql

SELECT *, field * field AS fieldName FROM table;

```

<br />

> ***" select 구에서 ,( comma ) 로 구분해 복수의 식을 지정할 수 있으며 각각의 식에 별병을 붙일 수 있습니다. "***
>

<br />

> ***" 키워드 as 는 생략할 수 있습니다. "***
>

<br />

> ***" ASCII 이외의 문자를 별명으로 사용할때 ""( double quote ) 를 사용한다. "***
>

<br />

> ***" ""( double quote ) 로 둘러싸면 명령구문을 분석할 때 데이터베이스 객체의 이름이라고 간주합니다.   
한편 ''( single quote ) 로 둘러싸는 것은 문자열 상수입니다. "***
>

<br />

> ***" 이름을 붙일 때는 숫자로 시작할 수 없습니다. "***
>

<br />

## WHERE 구에서 연산하기.

<br />

```sql

SELECT *, field * filed AS fieldName FORM table WHERE field * field >= 2500;

```

> 2500 보다 큰 record 를 조건으로 한다.   
	이때 where 에서 fieldName 을 참조해서 비교하면 될까 싶지만, 그렇게 되지 않는다. 이는 다음에서 보자.
>

<br />

## WHERE 구와 SELECT 구의 내부처리 순서.

<br />

> ***" 표준 sql 에는 내부 처리 순서가 따로 정해져 있지 않습니다. 하지만 where 구 -> select 구의 순서로 내부처리를 하는 데이터 베이스가 많습니다. 따라서 where 구로 행이 조건에 일치하는지 아닌지를 먼저 조사후에 select 구에 지정된 열을 선택해 결과를 반환하는 식으로 처리합니다. "***
>

<br />

p122 를 보자. 내부처리를 그림으로 잘 구현해 놓았다.

<br />

## NULL 값의 연산.

<br />

> NULL 로 연산하면 항상 NULL 이다.
>

## order by 구에서 연산하기.

<br />

```sql

SELECT *, field * field AS fieldName FROM table ORDER BY field * field DESC;

```

<br />

> ORDER BY 는 다음과 같이 내부처리가 이루어진다.   
   
	WHERE -> SELECT -> ORDER BY   
	   
	이 말은 as 를 통해 지정한 fieldName 을 사용할 수 있다는 말이다.
>

<br />

```sql

SELECT *, field * field AS fieldName FROM table ORDER BY fieldName DESC;

```

<br />

## 함수

>***" 연산자 외에 함수를 사용해 연산할 수도 있습니다. "***
>

<br />

```sql

functionName( parameter, parameter... );

```

<br />

## ROUND 함수

<br />

> 반올림 함수이다.
>

<br />

```sql

SELECT *, ROUND(value) FROM table;

```

<br />

> ROUND( 소수점값, 반올림 자리수 )
>

<br />

```sql

SELECT *, ROUND(value, 1) FROM table;

```

<br />

> 나머지는 집계와 서브쿼리에서 자세히 설명한다.
>
