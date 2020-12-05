# ch23 서브쿼리

<br />

>
***" 서브쿼리는 select 명령에 의한 데이터 질의로, 사웁가 아닌 하부의 부수적인 질의를 의미합니다. "***
>

<br />

## delete 의 where 구에서 서브쿼리 사용하기

<br />

```sql

DELETE FROM table WHERE field = ( SELECT MIN(a) FROM sample54 );
/* You can't specify target table 'sample54' for update in FROM clause 
	 이는 동일한 테이블을 서브쿼리에서 사용할수 없도록 되어 있기 때문이라고 한다. 이는 MySQL 과 MariaDB 에서 발생한다. 
 */

delete from ample54 where a=( select a from ( select min(a) as a from sample54 ) as x );

/*
	책에서는 이러한 에러를 발생시키지 않게 하기위해 인라인 뷰로 임시 테이블을 만들도록 처리하면 된다고 한다. 
 */

set @a = ( select min( a ) from sample54);
delete from sample54 where a=@a

/*
	위의 방식은 클라이언트 변수라 한다. 이 변수는 @a 이고 마치 임시테이블 처럼 사용가능하다. 
 */

```

<br />

```sql

( command ) /* <-- 이게 서브쿼리다. */

```

<br />

## 스칼라 값

<br />

>
***" select 명령이 하나의 값만 반환하는 것을 '스칼라 값을 반환한다.' 고 합니다. ***"
>

<br />

```sql

select min( field ) from table /* --> 스칼라 값 */

select min( field ), max( field ) from table /* --> 스칼라 값이 아니다. 여러 개의 field 를 가진다.*/

select field from table /* --> 스칼라 값이 아니다. 여러 개의 row 를 가진다.*/

/* 이처럼 하나의 값을 가진 테이블( field, row 가 하나. ) 이 스칼라이다.*/

```

<br />

p208 을 보자. 더 상세히 설명되어 있다.

<br />

>
***" 스칼라 값을 반환하는 서브쿼리를 특별히 '스칼라 서브쿼리' 라 부르기도 합니다. "***
>

<br />

>
***" '집계함수는 where 구에서는 사용할 수 없다' 라고 설명했습니다. 하지만 '스칼라 서브쿼리' 라면 where 구에서 사용할수 있으므로 집계함수를 사용해 집계한 결과를 조건식으로 사용할 수 있습니다. "***
>

<br />

## SELECT 구에서 서브쿼리 사용하기

<br />

>
***" 서브쿼리는 SELECT 구, UPDATE 의 SET 구 등 다양한 구 안에서 지정할 수 있습니다. "***
>

<br />

>
***" 문법적으로 서브쿼리는 '하나의 항목' 으로 취급합니다. 단, 문법적으로 문제없지만 실행하면 에러가 바생하는 경우가 자주 있습니다. 이는 스카라 값이 변환여부에 따라 생기는 현상으로. 서브쿼리를 사용할 때는 스칼라 서브쿼리로 되어 있는지 확인해야 합니다. "***
>

<br />

>
***" seleect 구에서 서브쿼리를 지정할 때는 스칼라 서브쿼리가 필요합니다. "***
>

<br />

```sql

SELECT
	( SELECT COUNT(*) FROM table ) AS sq1,
	( SELECT COUNT(*) FROM table ) AS sq2;

/* 주의할 점은 Oracle 이나 다른 데이터베이스에서는 select 구 이후에    
	 from 에서 테이블을 지정해 주어야 한다.   
	 이럴 경우 from dual 을 사용한다.    
	 dual 은 시스템 쪽에서 데이터베이승 기본 작성되는 테이블이라고 한다.*/

```

<br />

## FROM 구에서 서브쿼리 사용하기.

<br />

>
***" FROM 구에 기술할 경우에는 스칼라 값을 반환하지 않아도 좋습니다. "***
>

<br />

```sql

/* Oracle */
SELECT * FROM ( SELECT * FROM table ) sq;

/* MySQL, MariaDB */
SELECT * FROM ( SELECT * FROM table ) AS sq;

/*
 	Oracle 에서는 AS 를 붙이면 ERROR 난다. 
	하지만 MySQL 이나 MariaDB 에서는 AS 를 붙여도 된다.
 */
```

<br />

>
***" select 명령 안에 select 명령이 들어있는 듯 보입니다. 이를 '네스티드 구조' 또는 '중첩구조' 나  '내포구조' 라 부릅니다. "***
>

<br />

```sql

/* Oracle */
SELECT * FROM ( 
	SELECT * FROM table ORDER BY field DESC 
) sq WHERE ROWNUM <= 3;

```

<br />

>
NUMROW 는 WHERE 구에 의해 번호가 지정된다고 한다.   
이는 WHERE 를 통해 조건이 맞는 순서대로 번호가 부여된다는 이야기다.   
그러므로, 꼭 정렬되어 찾는다는 보장이 없다.   
이럴 경우 SUBQUERY 를 사용한다.   
SUBQUERY 를 사용하면 정렬후 NUMROW 로 제한할 수 있다.   
참고로 MariaDB 에서는 LIMIT 을 사용한다.   
>

<br />

## INSERT 명령과 서브쿼리

<br />

```sql

INSERT INTO table VALUES(
	( SELECT COUNT(*) FROM table_1 ),
	( SELECT COUNT(*) FROM table_2 )
);

SELECT * FROM table;

```

<br />

```sql

INSERT INTO table SELECT value, value;
SELECT * FROM table;

```
<br />

### - INSERT SELECT 

<br />

values 구 대신 select 명령을 명령을 사용할수 있다.   
이를 흔히 'insert select' 라 불리는 명령으로 insert 와 select 를 합친 것과 같은 명령이라 한다.   

<br />

>
***" insert select 명령은 select 명령의 결과를 insert into 로 지정한 테이블에 전부 추가합니다. "***
>

>
***" select 명령의 실행 결과를 클라이언트로 반환하지 않고 지정된 테이블에 추가하는 것입니다.  "***
>
<br />

그래서 데이터의 복사나 이동을 사용할 때 많이 사용하는 명령문이라 한다.
   
주의해야 할 점은 테이블의 field 수와 일치해야 한다는 것이다. 이건 매우 당연한 것이다.

