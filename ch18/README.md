# 데이터 갱신하기 UPDATE

<br />

>
***" 테이블의 셀에 저장되어 있는 값을 생신하려면 update 명령을 사용합니다. "***
>

<br />

```sql

UPDATE table SET field=value, field=value, ... WHERE cond;

```

<br />

## update 로 갱신할 경우 주의사항

<br />

```sql

UPDATE sample41 SET no=no+1;

```

<br />

>
set 구에서는 no 열의 값을 갱신하는데, 갱신 후의 값은 본래 값에서 1을 더한 값이다.
>

<br />

## SET 구의 실행

<br />

```sql
UPDATE sample4 SET no=no+1, a=no;
UPDATE sample4 SET a=no, no=no+1;
```

<br />

>
***" 이 두 update 명령은 콤마(.) 로 구분된 갱신 식의 순서가 서로 다릅니다. ... 데이터베이스 제품에 따라 그 처리 방식이 달라집니다. 다시 말해 데이터베이스 제품에 따라 결과가 달라지는 것입니다. "***
>

<br />

p171 을 살펴보자.

<br />


