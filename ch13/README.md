# CH13 문자열 연산

<br />

```sql

[+, ||, CONCAT] SUBSTING trim chracter_length

```

<br />

## 문자열 결합

<br />

| 연산자/함수 | 연산 | 데이터베이스 |
| :---: | :---: | :---: |
| + | 문자열 결합 | SQL Server |
| || | 문자열 결합 | Oracle, DB2, PostgreSQL |
| CONCAT | 문자열 결합 | MySQL |

<br />

```sql 

// MySQL
SELECT CONCAT( str1, str2 ) FROM table;

```

<br />

## SUBSTRING 함수

<br />

> ***" SUBSTRING 함수는 문자열의 일부분을 계산해 주는 함수입니다. "***
>

<br />

```sql

substring( '20201126', 1, 4 ); // 2020
substring( '20201126', 5, 2 ); // 11

```

<br />

## TRIM 함수

<br />

> ***" TRIM 함수는 문자열의 앞뒤로 여분의 스페이스가 있을 경우 이를 제거해주는 함수로 문자열 도중에 존재하는 스페이는 제거되지 않습니다. ***"
>

<br />

## CHRACTER\_LENGTH 함수

<br />

> ***" CHARACTER_LENGTH 함수는 문자열의 길이를 계산해 돌려주는 함수입니다. "***
>

<br />

> ***" CHAR_LENGTH 으로 줄여 쓸수 있다. "***
>

<br />

> ***" OCTET_LENGTH 는 문자열 길이를 byte 단위로 계산해 돌려준다. "***
>

<br />

그 이외의 문자셋 설명은 p135 를 보자. 그냥 ASCII 와 UTF-8 그리고 EUC-KR 에서의 바이트가 다르기에 참고하며 주의하라는 내용이다.

