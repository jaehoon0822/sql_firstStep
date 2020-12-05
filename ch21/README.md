# ch21 count 이외의 집계함수

<br />

## SUM 으로 합계구하기

<br />

```sql

SELECT SUM( field ) FROM table;

```

<br />

>
***" SUM 집계함수에 지정되는 집합은 수치형 뿐입니다. "***
>

>
***" SUM 집계함수는 COUNT 와 같이 NULL 값을 무시합니다. NULL 값을 제거한 뒤에 합계를 냅니다.  "***
>

<br />

## AVG 평균내기

<br />

>
AVG 집계함수에 주어지는 집합은 SUM 과 동일하게 수치형만 가능합니다.
>

<br />

```sql

SELECT AVG( field ) FROM table;
/* AVG 는 다음과 같다. */

SELECT SUM( field ) / COUNT( field ) FROM table;

```

<br />

## MIN, MAX 로 최대값, 최대값 구하기

<br />

```sql

SELECT MIN( num_field ), MAX( num_field ), MIN( str_field ), MAX( str_field ) FROM sample51;

```

<br />

>
***" 이들 함수는 문자열형과 날짜시간형에도 사용할 수 있습니다. 다만 NULL 값을 무시하는 기본규칙은 다른 집계함수와 같습니다. "***
>

<br />

