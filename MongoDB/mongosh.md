## MongoDB Shell

- show dbs
- use DB_NAME
- show collections

## Create

### method

- [insertOne()](https://docs.mongodb.com/manual/reference/method/db.collection.insertOne/#mongodb-method-db.collection.insertOne)
- [insertMany()](https://docs.mongodb.com/manual/reference/method/db.collection.insertMany/#mongodb-method-db.collection.insertMany)

### ordered

- `_id` field 중복 -> `duplicate key error`
- 여러 document 생성할 때 `duplicate key error` 발생한 경우 -> 이후 작업 중지
  - `{ "ordered": false }` 옵션 사용 시 -> 에러가 발생하지 않는 document를 모두 생성

## Read

### method

- [find(query, projection)](https://docs.mongodb.com/manual/reference/method/db.collection.find/#mongodb-method-db.collection.find)

### query

- 암시적 eq 연산자 사용
  - `db.inventory.find( { qty: { $eq: 20 } } )`
  - `db.inventory.find( { qty: 20 } )`
- 암시적 and 연산자 사용
  - `db.inventory.find( { "$and": [ { "status": "A" }, { "qty": { $lt: 30 } } ] )`
  - `db.inventory.find( { "status": "A", "qty": { $lt: 30 } } )`

### projection

- 지정한 field만 반환
  - `{ <field>: 1 }` : 포함
  - `{ <field>: 0 }` : 제외
  - `db.inventory.find( { "status": "A" }, { "item": 1, "status": 1, } )`

### array field

- value가 array일 경우 : 해당 array와 정확히 일치하는 document 검색
  - `db.inventory.find( { "tags": ["red", "blank"] } )`
- value가 element일 경우 : 해당 element를 포함하는 모든 document 검색
  - `db.inventory.find( { "tags": "red" } )`
- `$all` 사용 : 해당 element를 포함하는 모든 document 검색
  - `db.inventory.find( { "tags": { $all: ["red", "blank"] } } )`

## Update

### method

- [updateOne(filter, replacement, options)](https://docs.mongodb.com/manual/reference/method/db.collection.updateOne/#mongodb-method-db.collection.updateOne)
- [updateMany(filter, replacement, options)](https://docs.mongodb.com/manual/reference/method/db.collection.updateMany/#mongodb-method-db.collection.updateMany)
- [replaceOne(filter, replacement, options)](https://docs.mongodb.com/manual/reference/method/db.collection.replaceOne/#mongodb-method-db.collection.replaceOne)

### operators

- $inc : 지정한 양만큼 증가
- $set : field가 없다면 생성
- $push : array field에 추가

## Delete

### method

- [deleteOne()](https://docs.mongodb.com/manual/reference/method/db.collection.deleteOne/#mongodb-method-db.collection.deleteOne)
- [deleteMany()](https://docs.mongodb.com/manual/reference/method/db.collection.deleteMany/#mongodb-method-db.collection.deleteMany)
