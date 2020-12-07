# CH31 집합 연산

<br />

>
***" 복수의 테이블을 사용해 데이터를 검색하는 방법에 관해 알아보겠습니다. "***
>

<br />

## UNION 으로 합집합 구하기 

<br />

```sql

SELECT * FROM tableName_1 UNION SELECT * FROM tableName_2; 

```

<br />

>
***" 열 이름은 서로 다르지만 열 개수와 자료형이 서로 같기 때문에 일치한다고 말할 수 있습니다. 반면 완전히 열 구성이 다른 테이블을 UNION 으로 묶을 수 없습니다. "***
>

<br />

열 개수와 자료형만 맞으면 되므로 서로 일치하는 자료형을 가진 field 를 지정하여 묶을수 있다.

<br />

```sql

/* field 는 integer not null 타입이다.*/

SELECT field FROM table_1
UNION
SELECT field FROM table_2
UNION
SELECT field FROM table_3

/* 각 테이블의 field type 이 같으므로 UNION 으로 합집합을 구할 수 있다. */
```

<br />


### - UNION 을 사용할 때의 ORDER BY

<br />

>
***" UNION 으로 SELECT 명령을 결합해 합집합을 구하는 경우, 각 SELECT 명령에 ORDER BY 를 지정해 정렬할 수는 없습니다. ORDER BY 를 지정할 때는 마지막 SELECT 명령에만 지정하도록 합니다. "***
>

<br />


```sql

SELECT a AS c FROM table1
UNION
SELECT b AS c FROM table2 ORDER BY c;

```

<br />

table1 과 table2 의 field 가 다르므로 ORDER BY 시 잡을 기준 field 가 없다. AS 를 사용하여 각 field 의 합집합된 field 명을 만들어준다. ( field 명을 일치시켜준다. )

<br />

### - UNION ALL

<br />

>
***" 경우에 따라서는 중복을 제거하지 않고 2개의 SELECT 명령의 결과를 그냥 합치고 싶은 때도 있을 것입니다. 이러한 경우에는 UNION ALL 을 사용합니다. "***
>


<br />

>
***" UNION 의 경우는 기본동작이 DISTINCT 이고, 모든 결과를 얻고 싶을 때는 ALL 을 추가적으로 지정합니다. 즉, DISTINCT 나 ALL 로 중복제거 여부를 지정할 수 있다는 점은 같지만, UNION 기본동작은 ALL 이 아닌 DISTINCT 라는 점이 다릅니다. "***
>

<br />

```sql

select * from table1
union all
seelct * from table2;

```

<br />

## 교집합과 차집합

<br />

```sql

/* 교집합 */
SELECT * FROM table1
INTERSECT
SELECT * FROM table2;

/* 차집합 */
SELECT * FROM table1
EXCEPT
SELECT * FROM table2;

```

