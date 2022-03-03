## git

- 분산 버전 관리 시스템
  - 원격 저장소, 로컬 저장소
- 데이터를 파일 시스템 스냅샷의 연속으로 취급
  - 파일이 변경되지 않았다면 해당 파일의 링크만 저장
  - 마지막 커밋은 해당 시점의 스냅샷 전부 저장
  - 나머지 커밋은 델타(스냅샷 간 차이)를 저장 -> 저장소의 크기 작다

## git 파일 상태

### Untracked

- git이 추적하지 않는 파일
- 스냅샷, Staging Area에 모두 포함되지 않은 파일
- `git status` : Untracked files

### Tracked

- Unmodified
- Modified
- Staged
  - `git status` : Changes to be committed

## git 영역

### Working Directory

- 파일을 변경하는 영역

### Staging Area

- `staged` 상태의 파일들이 있는 영역

### Git Repository

- 파일의 변경 내역을 저장하는 영역
