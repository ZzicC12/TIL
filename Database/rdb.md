## RDB

- Relational Dababase
- row, column을 갖는 2차원 table을 중심으로 설계
- SQL을 통해서 관리

## key

### 기본 키 primary key

- 각 행을 유일하게 식별하는 값
- unique, NOT NULL

### 고유 키 unique key

- 중복된 값을 허용하지 않음

### 외래 키 foreign key

- table 간에 관계를 정의하는 외래 키

## 데이터 무결성 data integrity

- 데이터의 정확성과 일관성을 유지하고 보증하는 것

### 개체 무결성 entity integrity

- 기본 키는 unique AND NOT NULL

### 참조 무결성 reference integrity

- 기본 키와 외래 키 간의 관계가 항상 유지됨을 보장

### 영역 무결성 domain integrity

- 속성 값은 그 속성이 정의된 도메인에 속한 값이어야 함

## 제약 조건 constraint

- 데이터 무결성을 지키기 위한 조건

### 기본 키 제약 조건

- 기본 키는 unique AND NOT NULL

### 외래 키 제약 조건

- 참조되는 열은 unique OR 기본 키

### 유일 키

- NULL OR unique

### NOT NULL

- 값을 반드시 입력해야 함

### CHECK

- 범위, 조건 등 지정된 값만 허용
