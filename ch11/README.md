# CH11 결과행 제한하기 - LIMIT

<br />

```sql

SELECT field FROM table LIMIT recordNum[OFFSET 시작행]

```

<br />

> ***" LIMIT 구로 결과 행을 제한하는 방법. "*** 
>

<br />

## 행수 제한.

<br />

> ***" LIMIT 구는 표준 sql 이 아닙니다. mySQL 과 PostgreSQL 에서사용할 수 있는 문법이라는 점에 주의해 주세요. "***   
>

<br />

## 정렬한 수 제한하기

```sql

SELECT * FROM table ORDER BY field DESC LIMIT 3;

```
<br />

## LIMIT 를 사용할 수 없는 데이터베이스에서의 행 제한.

```sql 

SELECT * FROM table WHERE ROWNUM <= 3;

```

| meta character | 설명 |
| :---: | :---: |
| ROWNUM | 클라이언트에게 결과가 반환도리 때 각 행에 할당되는 행 번호. |

<br />

> ***" ROWNUM 으로 행을 제한할 때는 WHERE 구로 지정하므로 정렬하기 전에 처리되어 LIMIT 로 행을 제한한 경우와 결과값이 다릅니다. "***
>

<br />

## 오프셋 지정

<br />

> ***" 페이지 나누기 기능은 limit 을 사용해 간단히 구현할 수 있습니다. 한 페이지당 5건의 데이터를 표시하도록 한다면 첫 번째 페이지의 경우 limit 5 로 결과값을 표시하면 될 것 입니다. "***
>

<br />

> 만약 다음 페이지를 보고 싶다면, 이때 사용할 수 있는 위치를 가리키는 것이 ***OFFSET*** 이다.
>

<br />

```sql

SELECT * FROM table LIMIT 5 OFFSET 5;

```

> OFFSET 은0 부터 시작한다.
>



