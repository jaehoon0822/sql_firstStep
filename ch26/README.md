# ch26 테이블 작성,삭제,변경

<br />

```sql

CREATE TABLE tableName ( field, field, ... ); // 작성
DROP TABLE tableName; // 삭제
ALTER TABLE tableName subCommend // 변경

```

<br />

```sql

/* table 생성*/
CREATE TABLE tableName (
	id INTEGER NOT NULL, 
	a VARCHAR( 30 ),
	b DATE
	/* FIELD이름 TYPE [DEFAULT 기본값] [NULL/NOT NULL] */
);

```

<br />


## 테이블 삭제

<br />

>
***" 필요없는 테이블은 삭제할 수 있습니다. 이때 'DROP TABLE' 명령을 사용합니다. "***
>

<br />

```sql

DROP TABLE tableName;

```

<br />

### - 데이터 행 삭제

<br />

>
***" DELETE 명령은행 단위로 여러 가지 내부처리가 일어나므로 삭제할 행이 많으면 처리속도가 상당히 늦어집니다. 이런 경우 DDL 로 분류되는 'TRUNCATE TABLE' 명령을 사용합니다. "***
>
   
>
truncate: 자르다, 끝을 자르다, 일부를 생략하여 줄이다.
>

<br />

```sql

TRUNCATE TABLE tableName; // 모든행을 삭제

```

<br />

## 테이블변경

<br />

>
***" 테이블을 작성해버린 뒤에도 열 구성은 얼마든지 변경할 수 있습니다. 이때 테이블 변경은 'ALTER TABLE' 명령을 통해 이루어집니다. "***
>

<br />

```sql

ALTER TABLE tableName MODIFY fieldName type;

```

<br />

>
***" 기존의데이터행이 존재하는 경우, 속성 변경에 따라 데이터 역시 변환됩니다. 이때 만약 자료형이 변경되면 테이블에 들어간 데이터의 자료형 역시 바뀝니다. 다만 그 처리과정에서 에러가 발생하면 ALTER TABLE 명령은 실행되지 않습니다. "***
>

<br />

### - 열 이름변경

<br />

```sql

ALTER TABLE tableName CHANGE oldFieldName newFieldName;

/* Oracle 에서 RENAME TO 하부명령을 사용 /*

```

<br />

### - 열 삭제

<br />

```sql

ALTER TABLE tableName DROP fieldName;

```

<br />

## ALTER TABLE 로테이블 관리

<br />

p240 을보자.

<br />

### - 열추가

<br />

```sql

ALTER TABLE tableName ADD newField type;

```

<br />
