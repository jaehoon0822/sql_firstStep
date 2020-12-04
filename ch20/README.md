# CH20 행 개수 구하기 - COUNT

<br />

집계함수에 대해서 알아보자.

<br />

## COUNT 행 개수 구하기

<br />

>
***" sql 은 집합을 다루는 집계함수를 제공합니다. 일반적인 함수는 인수로 하나의 값을 지정하는 데 비해 집계함수는 인수로 집합을 지정합니다. "***
>

<br />

```sql

SELECT count(*) FROM table

```

<br />

count(\*) 집계함수는 ***'모든 열 = 테이블 전체'*** 라는 의미로 사용된다. 즉 COUNT 인수로 지정된 집합( 위 code 에서는 table 전체 ) 의 개수를 계산한다. 

<br />

>
***" 집계 함수의 특징은 복수의 값( 집합 ) 에서 하나의 값을 계산해내는 것입니다. "***
>

<br />

```sql

SELECT COUNT(*) FROM table WHERE cond;

```

<br />

## 집계함수와 NULL 값

<br />

>
***" 집계함수중 * 을 사용하는 함수는 COUNT 뿐이다. "***
>

<br />

>
***" 집계함수는 집합 안에 NULL 값이 있을 경우 무시한다. "***
>

<br />

## DISTINCT 로 중복제거

<br />

```sql

SELECT ALL field FROM table;
/* field 의 모든 값 선택 */

SELECT DISTINCT field FROM table;
/* field 의 중복 제거한 모든 값 선택*/

```

<br />

## 집계함수에서 DISTINCT 

<br />

ALL 과 DISTINCT 는 인수에서 수식자로 지정할 수 있다.

<br />

```sql

SELECT CONUNT( ALL field ), COUNT( DISTINCT field ) FROM table;

```

<br />

