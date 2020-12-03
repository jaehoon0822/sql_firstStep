# CH17 삭제하기 DELETE

<br />

>
***" 데이터베이스의 테이블에서 행을 삭제하기 위해서는 DELETE 명령을 사용합니다. "***
>

<br />

```sql

DELETE FROM table WHERE cond;

```

<br />

>
***주의점***   
   
WHERE 없이 DELETE 하면, 해당 테이블의 모든 정보가 삭제된다.   
항상 WHERE 절을 붙혀 사용한다.
>

<br />

## DELETE 명령 구

<br />

```sql

/* OR 키워드로 인해 두 조건모두 삭제한다. */
DELETE FROM table WHERE cond OR cond;

/* AND 키워드로 인해 두 조건모두 삭제한다. */
DELETE FROM table WHERE cond AND cond;

```

<br />

