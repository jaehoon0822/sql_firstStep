# CH22 그룹화 GROUP BY

<br />

>
***" 그룹화를 통해 집계함수와 활용범위를 넓힐수 있습니다. "***
>

<br />

## GROUP BY 로 그룹화

<br />

>
***" 열에서 같은 값을 가진 행끼리 한데 묶어 그룹화한 집학을 집계함수로 넘겨줄 수 있습니다. ***"
>

<br />

>
***" 그룹화하면 지정된 열의 값이 같은 행이 하나의 그룹으로 묶입니다. "***
>
   
>
***" GROUP BY 로 그룹화하면 DISTINCT 와 같이 중복을 제거한느 효과가 있습니다. "***
>

<br />

```sql

SELECT field, COUNT( field ), SUM( field ) FROM table GROUP BY field;

```

<br />

## HAVING 구로 조건 지정

<br />

>
***" 집계함수는 where 구의 조건식에서는 사용할 수 없습니다. where 구로 행을 검색하는 처리가 group by 로 그룹화하는 처리보다 순서상 앞서기 때문입니다. "***
>

<br />

### 구의 내부처리 순서

<br />

| 1 | 2 | 3 | 4 | 5 |
| :---: | :---: | :---: | :---: | :---: |
| WHERE 구 | GROUP BY 구 | HAVING 구 | SELECT 구 | ORDER BY 구 |

<br />

HAVING 은 집계한 결과의 조건에 맞는 값을 걸러낼 수 있는 구 이다.

<br />

이 책에서 select 구 의 실행이 group by 구와 having 구 보다 늦게 처리 되므로 as 를 사용한 aliase 를 사용할 수 없다고 한다. 하지만 일부 데이터베이스는 이러한 구문을 허락한다고 한다. ( MySQL, MariaDB 는 허용, Oracle 은 허용하지 않는다. )

<br />

MariaDB 에서는 가능하다.

<br />

```sql

SELECT field AS alias_n, COUNT( field ) AS alias_nc FROM talble GROUP BY alias_n HAVING cond;

```

<br />

## 복수열의 그룹화

<br />

>
***" GROUP BY 를 사용할 때 주으할 점이 하나 더 있습니다. GROUP BY 에 지정한 열 이외의 열은 집계함수를 사용할지 않는 채 SELECT 구에 기술해서는 안됩니다. "***
>

<br />

MariaDB 에서는 에러가 나지 않는다. 이 데이터베이스에서는 중복되는 field 의 값에서 첫번째 해당하는 값을 반환한다.

<br />

>
***" 집계함수를 사용하면 집합은 하나의 값으로 계산되므로, 그룹마다 하나의 행을 출력할 수 있습니다. ***"
>

<br />

## 결과값 정렬

<br />

GROUP BY 로 나온 결과값을 정렬하고 싶다면, ORDER BY 구를 사용하여 값을 정렬한다.

<br />

예시 p202 를 보자 
