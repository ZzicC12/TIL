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

## merge

### fast-forward

- 새로운 branch를 생성 후 master branch에 변동 사항이 없는 경우
- master branch의 포인터를 이동하는 작업만으로 merge 완료
- 커밋이 생성되지 않음
  - `--no-ff` 옵션 사용하여 커밋 생성 가능

### 3-way

- fast-forward 불가능한 경우 두 branch의 커밋을 합하여 새로운 커밋을 생성
