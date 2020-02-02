## flow없이 순수git으로만 협업하기

#### 팀장

```
- repo를 클론받음
- git branch develop생성
- touch 파일명
- git add 파일명
- git commit -m'feat:create파일명'
- git push -u oirigin develop
```

#### 팀원

```
- fork
# clone을 실행합니다.


- master가 branch되는 경우가 있음
# 이럴땐 당황하지말고 develop branch를 만들어서 실행하면 됩니다. - $ git branch develop으로 만들어서 진행하면 됨
- git checkout develop
- git branch feature/파일명
# 작업 후 develop으로 옮겨주기
- git checkout devlop 으로 이동한 후
- git merge feature/파일명
- git branch -D feature/파일명
#작업이 완료되면 기존에 있던 하위는 삭제


- $ git remote add pmorigin 팀장주소
- git pull pmorigin develop
- git add, commit, push 진행한 후 팀장에게 pullrequest 보내기
```

