## Git 기초

### 스냅샷

- git은 데이터를 스냅샷으로 취급한다.
- 여기서 스냅샷으로 취급한다는게 뭘까요?
  - 아직 git에 대해 깊게 공부하지 못해서 정확한 설명은 힘들지만 스냅샷은 커밋을 할 때마다 .git/objects에 생성되는걸 스냅샷이라고 합니다.
  - 파일의 내용을 변경하면 git은 기존에 있던 스냅샷과 비교해서 어떤 부분이 변경됐는 지를 파악합니다.
  - 조금 더 자세한 내용은 계속 공부하면서 알아가려고 합니다.
- 참고 : [git이 저장하는 방식 - 박준우블로그](https://junwoo45.github.io/2019-09-03-git%EC%9D%B4%EC%A0%80%EC%9E%A5%ED%95%98%EB%8A%94%EB%B0%A9%EC%8B%9D/), [what is a git snap shot - stackoverflow](https://stackoverflow.com/questions/4964099/what-is-a-git-snapshot)
