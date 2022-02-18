## MongoDB Shell

- show dbs
- use DB_NAME
- show collections

## Find

- db.COLLECTION_NAME.find()
  - count()
  - pretty()
  - it : iterate

## Insert

- db.COLLECTION_NAME.insert()
- `_id` field 중복 -> `duplicate key error`
- 여러 document 생성 시 `duplicate key error` 발생한 경우 -> 이후 작업 중지
  - `{ "ordered": false }` 옵션 사용 시 -> 에러가 발생하지 않는 document를 모두 생성

## Update

- db.COLLECTION_NAME.updateOne()
- db.COLLECTION_NAME.updateMany()
- operators
  - $inc : 지정한 양만큼 증가
  - $set : field가 없다면 생성
  - $push : array field에 추가

## Delete

- db.COLLECTION_NAME.deleteOne()
- db.COLLECTION_NAME.deleteMany()
- db.COLLECTION_NAME.drop()
