# ch16 행 추가하기 INSERT

<br />

## INSERT INTO 와 VLUES

>
	table 에 행을 추가하는 명령어
>

<br />

```sql

SELECT INTO table( field, field, ... ) VALUES( type, type, ... );

```
>
SELECT INTO 는 해당 열을 가리키고, VALUES 는 해당 열의 값을 지정한다.   
>

<br />

## NOT NULL 제약

<br />

>
VALUES 에 NULL 값을 할당할 수 있는데, 해당 FIELD 의 null 이 NO 로 설정되어 있다면, 제약이 걸려있다 할 수 있다. 이는 NULL 을 허용하지 않아 NOT NULL 제약 이라한다. 
>

<br />

## default 값

<br />

>
VALUES 에 값을 지정하지 않는다면, 미리 설정되어 있는 값이 할당된다. 이는 FIELD 의 DEFAULT 설정에 의해 값이 지정된다.
>

<br />

