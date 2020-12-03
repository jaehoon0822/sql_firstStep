# CH15 case 문으로 데이터 변환하기

<br />

## CASE 문

```sql

CASE 
	WHEN cond1 THEN expression1
	WHEN cond2 THEN expression2
	ELSE expression3
END

```

> 이렇게 쓰면 쉬운데 한줄로 쓰다보니, 헷갈린다.
>

```sql

SELECT field, case WHEN cond1 expression1 WHEN cond2 expresson2 ELSE expression3 END fieldName FROM table;

```

<br />

> 일반 프로그래밍 case 문과 비슷하다.
>

<br />

## COALESCE ( 유착하다, 합체하다 )

<br />

```sql

coalesce( expression1, ...n );


```

<br />

> COALESCE 는 여러 PARAMETER 를 갖는다. NULL 값이 아니라면 그중 가장 먼저 지정된 인수 값을 반환한다. 모든 값이 NULL 이면 NULL 을 리턴한다. 
>

<br />

```sql

SELECT field, COALECE( a, 0 ) FROM table;

```

<br />

## 또 하나의 CASE 문

<br />

> ***" case 문은 __단순 case__  와 __검색 case__ 로 나눌수 있습니다. "***
>

<br />

검색 CASE

```sql

CASE WHEN cond1 THEN expression 

```

<br />

단순 CASE

```sql

CASE expression WHEN expression THEN expression

```

<br />

> ELSE 는 생략하지 않고 지정하는것이 좋다. ELSE 를 생략하면 null 이 지정되므로, 항상 ELSE 를 지정하는것이 좋다.


<br />



