# CH6 검색 조건 지정하기

<br />

```sql

SELECT field1, filed2 FROM tableName WHERE conditional expression;

```

<br />

> ***" WHERE "*** 구를 사용하여 행을 선택한다.
>

<br />

> ***" SELECT "*** 구를 사용하여 열을 선택한다.
>

<br />

## SELECT 구에서 열 지정하기.

<br />

```sql

SELECT field1, field2 FROM tableName;

```

## WHERE 구에서 행 지정하기.

<br />

```sql

SELECT field FROM tableName WHERE conditional expression;

```

<br />

> ***" WHERE "*** 조건에 일치하는 행만 ***" SELECT "*** 의 결과로 반환
>

<br />

> ***" 조건식은 열과 연산자, 상수로 구성되는 식 입니다. "***   

	   
	조건식은 참이 되는 조건이다. '=' 연산자는 lvalue 와 rvalue 
	를 비교하고, 서로 같은 값이면 true 아니면 false 를 반환한다. 비교 연산이라는 뜻이다. ( 변수의 할당 연산자가 아니라는 점을 알아두자. )
>

<br />

> "<>" 연산자는 lvalue 와 rvalue 의 값이 같지 않을때, ture 를반환한다. 그러므로 "=" 와 반대이다.
>

## 문자열형 상수

<br />

```sql

SELECT * FROM tableName WHERE name='string';

```

<br />

> 문자열 상수를 조건식으로 평가할때 ''( single quote ) 를 사용하여 검색해야 한다. 
>

<br />

> 날짜시간형역시 ''( single quote ) 로 둘러싸 표기한다.
>

> 시간은 :( colon ) 으로 구분하여 표기한다.
>

```sql

SELECT field FROM tableName WHERE dayAndTime='2020-11-26 02:00:00';

```

<br />

> 조건식의 비교를 위해서 type 에 맞추어 지정해야 한다.
>

<br />

## NULL 값 검색

<br />

```sql

SELECT filed FROM tableName WHERE birthday=NULL;

```

> 검색안됨.
	"=" 연산자로 NULL 값을 검색할 수 없다.
>

<br />

```sql

SELECT * FROM tableName WHERE birthday IS NULL;

```

<br />

> ***" IS NULL "*** 을 사용하면, lvalue 가 NULL 일 경우 true 를 반환한다.
>

<br />

> ***" IS NOT NULL "*** 은 lvalue 가 NULL 이 아닐때 true 를 반환한다.
>

<br />

## 비교 연산자

<br />

> ***- ( = 연산자 ) -***   
	lvalue 와 rvalue 를 비교. 같을경우 ture
>

<br />

> ***- ( <> 연산자 ) -***   
	lvalue 와 rvalue 를 비교. 다를경우 ture
>

<br />

> ***- ( > 연산자 ) -***   
	lvalue 와 rvalue 를 비교. lvalue 가 더 클경우 ture
>

<br />

> ***- ( >= 연산자 ) -***   
	lvalue 와 rvalue 를 비교. lvalue 가 더 크거나 같을경우 ture
>

<br />

> ***- ( < 연산자 ) -***   
	lvalue 와 rvalue 를 비교. rvalue 가 더 클경우 ture
>

<br />

> ***- ( <= 연산자 ) -***   
	lvalue 와 rvalue 를 비교. rvalue 가 더 크거나 같을경우 ture
>

<br />

