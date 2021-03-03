## 브랜치란 무엇인가

이번 쳅터는 어려워서 여러번 읽어봐야할 것 같다.

Git이 브랜치를 다루는 과정을 이해하려면 Git이 데이터를 스냅샷으로 기록한다는 것에 주목해야 한다.

사용자가 변경 내용을 커밋하면 Git은 `**커밋 개체(commit object)**`를 저장하는데 이 객체에는

1. 현 Staging Area에 있는 데이터의 스냅샷에 대한 **포인터**
2. 저자나 커밋 메세지 같은 **메타데이터**
3. **이전 커밋에 대한 포인터**
   등이 포함되 있다.

우리는 커밋 개체의 이전 커밋 포인터가 있기 때문에 **현재 커밋이 무엇을 기준으로 바뀌었는지를 알 수 있다**. 최초 커밋을 제외한 나머지 커밋은 이전 커밋 포인터가 적어도 하나씩은 있고, 여러 브랜치를 합친 Merge 커밋 같은 경우에는 이전 커밋 포인터가 여러개 있다.

새로 생성한 파일도 있지만 3개의 파일을 Staging Area에 저장하고 커밋하는 예제를 살펴보자. 먼저 어떤 파일이 있는지를 이야기해보면 루트 디렉토리에 있던 `README.md`과 이번에 새로 시작한 chapter3와 관련된 파일들이 있다.

```
$ git status
현재 브랜치 main
브랜치가 'origin/main'에 맞게 업데이트된 상태입니다.

커밋하도록 정하지 않은 변경 사항:
  (무엇을 커밋할지 바꾸려면 "git add <파일>..."을 사용하십시오)
  (use "git restore <file>..." to discard changes in working directory)
	수정함:        README.md

추적하지 않는 파일:
  (커밋할 사항에 포함하려면 "git add <파일>..."을 사용하십시오)
	chapter3/

커밋할 변경 사항을 추가하지 않았습니다 ("git add" 및/또는 "git commit -a"를
사용하십시오)
```

파일을 `Stage`하면 Git 저장소에 파일을 저장하고(Git은 이걸 Blob이라고 부른다) `Staging Area`에 해당 파일의 체크섬을 저장한다.

- 여기서 파일을 `Stage`한다는 것은 `git add` 명령을 통해 각각의 체크섬이 생성되고
- `Git Repository`(.git directory)에 해당 버전의 파일을 저장한다는 것(Blob)
- 그리고 `Stating Area`에 체크섬을 저장한다.
- 조금 헷갈리는게 `Git Repository`에 파일을 저장하는 것과 `Staging Area`에 체크섬을 저장하는 것을 왜 구분 할까?
  - 이 문제는 좀 더 공부 한 후 고민해보자

```
git add README.md chapter3/
git commit -m '2021.03.03 chapter3 - git branches'
```

- `git commit` 명령을 통해 커밋을 생성하면, 루트 디렉토리와 하위 디렉토리의 체크섬을 만들고 Git repository에 `tree object`로써 저장된다. 즉 여기서 `Git repository`에 저장된 `tree object`에 들어 있는 건 디렉토리의 `**체크섬**`!
