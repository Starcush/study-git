## Chapter2 Git Basic

### 학습목표

- [x] 저장소를 만들고 설정하는 방법
  - `git clone` 명령 혹은 `git init` 명령을 사용해서 `.git` 디렉토리를 생성하면 이때부터 저장소로써 사용이 가능하다.
- [x] 파일을 추적(track)하거나 추적을 그만두는 방법
  - `git add`명령을 통해 추적할 파일을 정하면 Git은 파일을 추적하기 시작한다. 만약에 추적을 그만두고 싶다면 `git rm` 명령을 통해 취적을 취소시킬 수 있다.
- [x] 변경 내용을 stage하고 커밋하는 방법
  - Git이 추적하고 있는 파일을 변경했다면 `git add`명령을 통해 `Staging Area`에 올려두고 `git commit` 명령을 통해 커밋이 가능하다.
- [x] 파일 패턴을 무시하도록 git을 설정하는 방법
  - Git이 파일 패턴을 무시하도록 하는 방법은 `.gitignore`파일에 무시하고자 하는 파일 패턴을 추가하면 된다. 작성 요령은 표준 Glob 패턴을 따른다.
- [x] 실수를 만회하는 방법
  - 아직 내가 원하는 정도의 실수를 만회하는 방법은 안나온 것 같지만
  - 이미 커밋했지만 내용을 추가하고 싶을 때는 `git commit --amend`, 커밋하려고 `staged`한 파일을 취소하는 방법은 `git reset`명령을 사용한다.
- [x] 프로젝트 히스토리를 조회하고 커밋을 비교하는 방법
  - `git log`를 사용하면 지금까지의 히스토리를 확인할 수 있고, `git diff`를 사용하면 커밋한 내용을 비교할 수 있다.
  - `git log`의 다양한 옵션을 상용하면 보다 다양한 방법으로 편리하게 히스토리를 확인할 수 있다. 이를 위해서는 `git alias`를 이용해서 긴 명령을 짧게 사용하자.
- [x] 리모트 저장소에 push, pull 하는 방법
  - 로컬에서 수정한 내용을 리모트 저장소에 전달 할 경우에는 `git push`, 다른 사람이 변경해서 리모트 저장소에 저장한 것을 로컬에 가져오는 건 `git pull`명령을 사용한다.
  - 단, `git pull`의 경우 `git fetch`와 `merge`를 동시에 적용한다.
