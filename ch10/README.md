# CH10 복수의 열을 지정해 정렬하기.

<br />

```sql

SELECT filed FORM tableName WHERE cond ORDER BY FIELD [ASC|DESC], ,FIELD [ASC|DESC];

```

<br />

## 복수 열로 정렬 지정.

<br />

> ***" '순서는 일정하지 않다.' 데이터베이스 서버의 당시 상황에 따라 어떤 순서로 행을 반환할지 결정합니다. 따라서 언제나 같은 순서로 결과를 얻고 싶다면 반드시 ORDER BY 구로 순서를 지정해야 합니다. "***
>

<br />

## ORDER BY 로 복수 열 지정하기.

<br />

> ***" order by a, b 로 지정해 먼저 a 로정렬하고, 값이 같은 부분은 b 열로 지정됩니다. "***
>

<br />



> ***" b, a 와 같이 열 지정 순서를 바꾸면, b 열에서 값의 크기 순서대로 정렬되고, 값이 같은 부분은 a 열로 정렬된다.  "***
>

<br />

## NULL 값의 정렬순서

<br />

> ***" ORDER BY 로 지정한 열에서 NULL 값을 가지는 행은 가장 먼저 표시되거나 가장 나중에 표시됩니다. null 값의 대소비교 방법은 표준 SQL 에도 규정되어 있지 않아 데이터베이스 제품에 따라 기준이 다릅니다. ***" 
>


