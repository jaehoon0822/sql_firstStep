# CH7 조건 조합하기

<br />

```sql

conditionalExpression AND conditionalExpression;
conditionalExpression OR conditionalExpression;
NOT conditionalExpression;

```
<br />

> 통상적으로2개 이상의 조건식을 조합해 검색하는 경우가 많다. 
	조건식을 조합해 사용할 경우 복수의 조건을 WHERE 구로 지정한다.
>

<br />

## AND 로 조합하기

<br />

```sql

SELECT * FROM tableName WHERE	cond1 AND cond2;

```

<br />


## OR 로 조합하기

<br />

```sql

SELECT * FROM tableName WHERE cond OR cond;

```

<br />

## 연산자 우선수위

> ***" or 보다 and 연산자의 우선순위가 높다. "***   
	그러므로 구룹 연산자() 를 사용하여 우선순위를 높혀 사용해야 하는 경우가 존재한다.
>

```sql

SELECT * FROM tableName WHERE cond OR cond AND cond OR cond;

```

<br />

> 위의 코드에서는 and 먼저 평가하고 나머지 or 을 평가한다.   

	or 먼저 평가하고 싶다면, 그룹 연산자로 묶어주어야 한다.
>

<br />

```sql

SELECT * FROM tableName WHERE (cond OR cond) AND (cond OR cond);

```

## NOT 으로 조합

<br />

```sql

NOTcond;


```

<br />

> ***" not "*** 연산자는 오른쪽에만 항목을 지정하는 단항 연산자다. 해당 조건식을 반대로 평가한다.
>

```sql

SELECT * FROM tableName WHERE NOT(cond AND cond);

```

