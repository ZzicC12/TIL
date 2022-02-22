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

## BASE

### Basically Available

- 가용성
- 다수의 스토리지에 복사본을 저장

### Soft state

- 시스템의 상태는 시간이 지남에 따라 변할 수 있음
- 분산 노드 간 업데이트는 데이터가 노드에 도달한 시점에 갱신

### Eventually consistent

- 일시적으로 비일관적인 상태가 되어도 결국 일관성이 있는 상태가 되는 성질
