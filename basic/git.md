1. 원격저장소에 branch 만들기/삭제하기
```
# local
$ git checkout -b branch-name   # local branch create  
$ git branch -D branch-name     # local branch delete

# origin (remote)
$ git push origin branch-name   # remote branch create
$ git push origin :branch-name  # remote branch delete
```
2. git 디렉토리별 계정 설정
```
$ git config --list  # 설정 확인
$ git config --local user.name "user-name" # 해당하는 repo에서 local 설정 
$ git config --local user.email "email@abc.com"

## globla 세팅은 옵션을 --global으로 주면 된다
```

3. 프로젝트 생성 후 푸시 할 때 unable to access 'url' the requested URL returend error : 403 오류 발생
```
# 푸시 할 때 원격저장소에 권한이 없어서 발생 => set url 세팅 후 푸시 재시도, 인증 진행
$ git remote set-url origin "https://{username}@github.com/{username}/{repo-name}.git" 
```

4. git reset 을 했는데 되돌리고 싶을 때
```
$ git reflog         # reflog 확인
$ git reset HEAD@{1} # 되돌리고 싶은 head로
```

![reflog확인](../../images/reflog.png)

5. git에 빈 디렉토리를 추가하고 싶을 때 
   - 빈 디렉토리에 아래 gitignore 파일을 추가해서 가능하다
   - [해당 내용 출처](https://www.lesstif.com/gitbook/git-add-23757005.html)
```
## 모든 파일 ignore
*
# .gitignore 는 추가
!.gitignore
```

6. Git dafult branch가 master -> main으로 바뀜
   - 변경 하고 싶을 땐 github repository > settings > branches > Default branch 에서 가능

