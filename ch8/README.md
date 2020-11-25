# 패턴 매칭에 의한 검색

<br />

> ***" LIKE "*** 술어를사용하면 문자열의 일부분을 비교하는 "부분검색" 을 할수 있다.
>

<br />

```sql

field LIKE 'pattern';

```

<br />


| meta character | 의미 |
| :---: | :---: |
| % | 임의의 문자열을 의미 |
| _ | 임의의 문자 하나를 의미 |
| \ | 이스케이프 문자 |
| ' | 문자열 이스케이프 문자 |

<br />

```sql

select * from tableName where fieldName like '%\%%';
select * from tableName where fieldName like 'It''t';

```





