# CH27 제약

<br />

## 테이블작성시 제약 정의

<br />

```sql

create table tableName (
	field1 TYPE NOT NULL,
	field2 TYPE NOT NULL UNIQUE, /* not null, unique 제약*/
	field3 TYPE
);

```

<br />

>
***" 열에 대해 정의하는 제약을 '열 제약' 이라 부릅니다.  "***
>

<br />

```sql

CREATE TABLE tableName (
	field1 TYPE NOT NULL,
	field2 TYPE NOT NULL,
	PRIMARY key( field1, field2 )
);

```

<br />

>
***" 복수의 열에 제약을 설명하는 경우를 '테이블 제약' 이라 부릅니다. "***
>

<br />

>
***" 제약 이름을 붙이면 나중에 관라히가 쉬워지므로 가능한 한 이름을 붙이도록 합니다. 제약 이름은 'CONSTRAINT' 키워드를 사용해서 지정합니다.   "***
>

<br />

```sql

CREATE TABLE tableName (
	field1 TYPE NOT NULL,
	field2 TYPE NOT NULL,
	CONSTRAINT name PRIMARY key( field1, field2 )
);

```

<br />

## 제약추가

### - 열 제약 추가

<br />

```sql

ALTER TABLE tableName MODIFY field TYPE NOT NULL;

```

<br />

>
***" ALTER TABLE 로 열 정의를 변경할 수 있습니다.  "***
>


<br />

### - 테이블 제약 추가

<br />


```sql

ALTER TABLE tableName ADD CONSTRAINT key PRIMARY KEY( filed );
/* 기본 키 설정 */

```

<br />

>
***" ALTER TABLE 의 ADD 하부명령으로 추가할 수 있습니다. "***
>

<br />

## 제약 삭제

<br />

```sql

ALTER TABLE tableName MODIFY field type;
/* 해당 열에 있는 제약이 있다면 MODIFY 로 재수정한다. */
/* 재약삭제와 같다. */

```

<br />

```sql

ALTER TABLE tableName DROP CONSTANT key;
/* 제약명을 사용해 삭제 */

ALTER TABLE tableName DROP PRIMARY KEY;
/* MySQL 에서 기본키는 테이블당 하나만 설정할 수 있기 때문에 굳이 제약명을 지정하지 않고도 삭제할 수 있다고 한다.*/
```

<br />

## 기본키

<br />

>
***" 기본키로 지정해 유일한 값을 가지도록 하는 구조가 바로 기본키 제약 입니다. "***
>

<br />

```sql

CREATE TABLE tableName (
	field1 TYPE NOT NULL,
	field2 TYPE,
	constraint pkey primary key( field1 )		
); /* constraint 로 제약명 설정, primary key 를 사용하여 field1 을 기본키 지정*/

	/* praimary key 로 지정된 field 는 값이 유일해야 한다. */

```

<br />

>
***" 행이 유일성을 필요로 한다는 의미에서 '유일성 제약' 이라 불리는 경우도 있습니다. "***
>

<br />

### - 복수의 열로 기본키 구성하기 

<br />

>
***" 기본키 제약에는 이를 구성할 열 지정이 필요합니다. 이때 지정된 열은 NOT NULL 제약이설정되어 있어야 합니다. "***
>

<br />

>
***" 기본키를 구성하는 열은 복수라도 상관없습니다. 복수의 열을 기본키로 지정했을 경우, 키를 구성하는 모든 열을 사용해서 중복하는 값이 있는지 없는지를 검사합니다. "***
>

<br />
