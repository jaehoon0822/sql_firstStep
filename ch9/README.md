# CH9 정렬- ORDER BY

<br />

> ***" select 명령의 order by 구를 사용하여 검색결광의 행 순서를 바꿀수 있습니다.  "***   
>

<br />

```sql

SELECT field FROM tableName WHERE cond ORDER BY field
	
```

<br />

## ORDER BY 로 검색결과 정렬하기.

<br />

```sql

SELECT filed FROM tableName ORDER BY age;

```

<br />

| 정렬 meta character | 설명 |
| :---: | :--:- |
| DESC ( descendant ) | 내림차 |
| ASC ( ascendant ) | 오름차 |

<br />

```sql

SELECT filed FROM tableName ORDER BY fieldName DESC;
SELECT filed FROM tableName ORDER BY fieldName ASC;

```

## 대소관계

<br />

> ***" 수치형 데이터라면 대소관계는 숫자의 크기로 판별합니다. "***
>

<br />

<br />

> ***" 문자열형 데이터의 대소관계는 사전식 순서에 의해 결정됩니다.  "***
>

<br />

## order by 는 테이블에 영향을 주지 않는다.

<br />

> ***" order by 는 행의 순서를 바꾸어 결과를 반환하는 것뿐, 저장장치에 저장된 데이터의 행 순서를 변경하는 것은 아닙니다. "***
>

