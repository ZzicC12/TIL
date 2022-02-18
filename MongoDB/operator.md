## Comparison Opertaors

- $eq, $ne
- $gt, $lt
- $gte, $lte

### 형식

- `{ <field>: { <operator>: <value> } }`
  - `{ "pop": { "$lt": 1000 } }`
- operator 생략 시 $eq 사용
  - `{ "type": { "$eq": "Customer" } }`
  - `{ "type": "Customer" }`

## Logic Operators

- $and
- $or
- $nor
- $not

### 형식

- `{ <operator>: [{ }, { }, ...]}`
  - `{ "$and": [ { "result": "Out of Business" }, { "sector": "Home Improvement Contractor - 100" } ] }`
- 동일한 field에 대한 query일 경우 and 생략 가능
  - `{ "$and": [ { "student_id": { "$gt": 25 } }, { "student_id": { "$lt": 100 } } ] }`
  - `{ "student_id": { "$gt": 25, "$lt":100 } }`

## Expressive Query Operator

- `aggregation expression` 사용 가능하게 함
- 표현식을 통해 document 내 field 끼리 비교 가능

### $ 역할

- 연산자 앞에 사용
- 해당 field의 value를 의미

### 형식

- `{ "$expr": { <expression> } }`

## Array Operator

- $push : 배열에 추가 OR 해당 field를 배열로 바꿈
- $all
- $size
- $elemMatch

## Projection

## Nested Document
