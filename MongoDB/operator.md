## Comparison Query Operators

- `{ <field>: { <operator>: <value> } }`
- $eq, $ne
- $gt, $lt
- $gte, $lte

## Logical Query Operators

- $and
- $or
- $nor
- $not

- 동일한 field에 대한 query일 경우 and 생략 가능
  - `{ "$and": [ { "student_id": { "$gt": 25 } }, { "student_id": { "$lt": 100 } } ] }`
  - `{ "student_id": { "$gt": 25, "$lt":100 } }`

## Expressive Query Operators

- `{ "$expr": { <expression> } }`
- `aggregation expression` 사용 가능하게 함
- 표현식을 통해 document 내 field 끼리 비교 가능

### $ 역할

- 연산자 앞에 사용
- 해당 field의 value를 의미

## Array Query Operators

- $all
- $size
- $elemMatch
