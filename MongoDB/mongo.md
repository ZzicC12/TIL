## MongoDB

- document 기반의 NoSQL DB
- document -> collection -> DB
- BSON 형식으로 데이터를 저장

### Document

- 데이터를 field, value 쌍으로 관리
- 모든 document에는 `_id` field 존재
  - ObjectId 타입
  - collection 내에서 unique
  - document 생성 시 자동으로 field 생성

### JSON BSON

|        |                 JSON                 |                            BSON                            |
| :----: | :----------------------------------: | :--------------------------------------------------------: |
| 인코딩 |                UTF-8                 |                           Binary                           |
|  타입  | String<br>Boolean<br>Number<br>Array | String<br>Boolean<br>Number<br>Array<br>Date<br>Raw Binary |

## MongoDB Atlas

- 클라우드 DB
- MongoDB Shell(mongosh)로 원격 접속 가능
