## 브랜치와 Merge이 기초

일반적으로 브랜치로 merge를 활용하는 방법은 다음과 같다.

1. 작업 중인 웹 사이트가 있다.
2. 새롭게 처리할 이슈가 생겨서 새 `branch`를 만든다.
3. 새로 만든 `branch`에서 작업을 한다.

이때 `production` 브랜치에서 급하게 고칠 문제가 생겨서 `hotfix` 브랜치를 만들어야 한다. 그러면 아래와 같이 할 수 있다.

4. `production` 브랜치로 돌아간다.
5. `hotfix` 브랜치를 새로 생성한다.
6. `hotfix`로 새로운 이슈를 해결하고 `production` 브랜치에 `merge`한다.
7. 기존에 작업하던 2번에서 생성한 브랜치로 돌아가 작업을 한다.

### 브랜치의 기초

상황에 맞게 브랜치를 생성하고 이동하는 것을 `progit`에 나와있는 예제가 아닌 현재 프로젝트를 기준으로 생각해보려 한다.
지금까지 `main` 브랜치에 모든 작업을 하고 있었는데 오늘 `branch`의 `merge`에 대해 공부한 내용을 새로운 브랜치를 생성해서 작업하고 싶었고 `git-branch-merge`라는 새로운 브랜치를 만들고 싶다

```
$ git switch -c git-branch-merge
```

- `progit`에는 `git checkout` 명령어를 사용했지만 `git`의 `2.23.0`버전에서 `checkout`의 기능을 `switch`와 `restore`로 분리했기 때문에 브랜치의 생성 및 이동과 관련된 건 `git switch`를 사용하고 있다.
- 관련된 내용
  - [Outsider's Dev Story - 새 버전에 맞게 git checkout 대신 switch/restore 사용하기](https://blog.outsider.ne.kr/1505)
  - [honeymon.io - [Tech] Git 2.23.0 출시: checkout 기능 분리(switch, restore)](http://honeymon.io/tech/2019/08/30/git-2.23-release.html)
