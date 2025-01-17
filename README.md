![DB](https://noticon-static.tammolo.com/dgggcrkxq/image/upload/v1567061412/noticon/lzcrj8bbwgu55lddwiz6.png){: width="100"}

# DataBase modeling

## 데이터베이스 모델링 정의

#### 1. DB(DataBase) 와 DB 관리 시스템(DBMS)은 다른 개념이다.

- **DB** : 데이터를 저장하는 공간
- **DBMS** : DB를 관리하는 시스템

#### 2. 데이터베이스 모델링은 데이터베이스를 설계하는 과정이다.

- 데이터를 잘 분류해서 저장하는 방안을 고려하는 과정이다.
- 분류의 기준은 데이터의 종류, 특성, 관계 등이 있다.
- 데이터를 쉽게 저장, 검색, 수정, 삭제하는 것이다.

#### 3. 데이터베이스 모델링의 최종 목적

- 데이터의 중복을 최소화하고 데이터의 일관성을 유지하는 것이다.
- 데이터의 무결성을 보장하는 것이다.

#### 4. 관계(Relation)형채의 데이터베이스 모델링

- RDBMS(관계형 데이터베이스 관리 시스템)
- 데이터를 테이블(Table)로 표현하는 모델링 방법이다.
- 테이블은 행(Row)과 열(Column)로 구성된다.
- 행은 레코드(Record)라고 부른다.
- 열은 필드(Field)라고 부른다.
- 테이블은 키(Key)로 구분된다.
- 테이블은 관계(Relation)로 연결된다.
- `MySQL`, `Oracle`, `PostgreSQL`, `SQL Server` 등이 있다.

## 데이터베이스 모델링 과정

### 1. 요구사항 분석

- 서비스 기획 단계에서 고객 요구사항을 분석한다.
- 문장으로 된 다양한 서비스 내용에 대해서 대표적 속성(Attribute)을 추출한다.
- 요구사항 정의서를 작성한다.
- 추출된 속성(Attribute)을 이용해서 하나의 개체(Entity)를 분류한다.
- 개체(Entity) 간의 관계(Relationship)를 분석한다.
- 이러한 개체(Entity)들을 묶어서 하나의 스키마(Schema)를 만든다.

### 2. 개념적 데이터 모델링

- **Entity Relationship Diagram**(ERD)
- 개체(Entity)와 관계(Relationship)를 이용해서 데이터베이스의 개념적 구조를 표현한다.
- 개체(Entity)는 테이블(Table)로 표현한다.
- 관계(Relationship)는 테이블과 테이블 사이의 관계를 나타낸다.

### 3. 논리적 데이터 모델링

- Excel 활용 및 PK(Primary Key), FK(Foreign Key) Relation Model 설정

### 4. 물리적 데이터 모델링

- 테이블 정의서, SQL Script 작성

### 5. 데이터베이스 구축

- **Reverse Engineering** : 역으로 추적하여 처음의 문서나 설계기법 등의자료를 얻어내는 일

- **Forward Engineering** : eXERD 프로그램으로 DB를 모델링한 후 DB모델을 MS-SQL 또는 Oracl, MySQL 등 데이터베이스 프로그램에 모델을 자동으로 등록해주는 기능

## 데이터베이스 모델링 실습

### 1. 중복되는 데이터 제거

- Schema 폴더 생성
  : 소문자 폴더로 저장

- Entity (객체)를 파일로 Table 생성
  : 소문자(복수형)로 생성

- 속성(Attribute) 생성
  : 소문자로 칼럼명을 생성

- 속성 PK(Primary Key)
  : PK(Primary Key) 속성은 절대 중복되지 않는 조건
  : 자동 증가 또는 유니크 속성을 부여해야 한다.
  : 자동 증가는 auto_increment 속성을 부여해야 한다.
  : 유니크 속성은 uuid 속성을 부여해야 한다.

- 속성 FK(Foreign Key)
  : FK(Foreign Key) 속성은 외래키 속성이다.
  : 다른 테이블 즉, Entity와 관계를 연결시키는 키다.
  :일반적으로 다른 테이블의 PK가 연결된다

### 2. 데이터 값은 1개만 존재한다.

- 데이터베이스의 레코드가 다중 값을 가지는 경우
  : 개별 레코드를 분리하여 FK(Foreign Key)로 연결한다
  : 다중의 FK가 필요한 경우에는 중간 테이블(Junction Table)을 생성하여 N:M 관계를 구현한다

### 3. 대응수(Cardinality)

**대응수란?**
: 하나의 테이블이 다른 테이블의 FK(Foreign Key)로 연결되는 경우
: 1:1, 1:N, N:1, N:N 등이 있다.

**대응수 관계 예시**

- A와 B의 관계
- A는 B를 소유하고 있다.
- B는 A에게 소유되어 있다.
- 하나의 A는 하나 혹은 여러개의 B를 소유하고 있다.

  **1:N 구조 관계**

  - 회원과 이메일의 관계
  - 회원은 이메일을 소유하고 있다.
  - 이메일은 회원에게 소유되어 있다.
  - 한명의 회원은 이메일을 소유하고 있다.
  - 한명의 회원은 여러개의 이메일을 소유하고 있다. (1 : N)
  - 하나의 이메일은 한명의 회원에게 소유되어 있다. (1 : 1)
