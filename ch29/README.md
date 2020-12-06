# CH29 인덱스 작성과 삭제

<br />

```sql

CREATE INDEx
DROP INDEX

```

<br />


## 인덱스 작성

<br />

>
***" Oracle 이나 DB2 등에서 인덱스는 스키마 객체가 됩니다. "***
>

<br />

>
***" SQL Server 나 MySQL 에서 인덱스는 테이블 내의 객체가 됩니다. "***
>

<br />

>
***" 인덱스를 작성할 때는 해당 인덱스가 어느 테이블의 어느 열에 관한 것인지 지정할 필요가 있습니다. 이때 열은 복수로도 지정할 수 있습니다.  "***
>

<br />

```sql

CREATE INDEX indexName ON tableName( field, field, ... );

```

<br />

## 인덱스 삭제

<br />

```sql

DROP INDEX indexName ON tableName;

```

<br />

>
***" 인덱스는 테이블에 의존하는 객체입니다. DROP TABLE 로 테이블을 삭제하면 테이블에 작성된 인덱스도 자동으로 삭제됩니다. "***
>

<br />

## EXPLANE

<br />

```sql

EXPLAIN SQL 명령

```

<br />

>
***" 어떤 상태로 실행되는지를 데이터베이스가 설명해줄 뿐입니다.  "***
>

<br />

>
***" EXPLAIN 은표준 SQL 에는존재하지 않는, 데이터베이스 제품 의존형 명령입니다.  "***
>

<br />

결과   
   
| id | select\_type | table | type | possible\_keys | key | key\_len | ref | rows | Extra |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | simple | sample62 | ref | isample62 | isample62 | 92| const | 1 | Using where; Using index |

<br />

p261 에서 잘 설명되어 있다.

<br />

## 최적화

<br />

>
***" 내부 처리에서는 SELECT 명령을 실행하기에 앞서 실행계획을 세웁니다. 실행계획에서는 '인덱스가 지정된 열이 WHERE 조건으로 지정되어 있으니 인덱스를 사용하자' 와 같은 처릭 이루어집니다.  EXPLAIN 명령은 이 실행계획을 확인하는 명령입니다. "***
>

<br />



