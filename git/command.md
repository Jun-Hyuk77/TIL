# git command

> 기본 명령어를 정리

​            [         ![img](command.assets/git_three_tree.png)       ](https://seunghyum.github.io/assets/images/posts/git_three_tree.png)        

##### init

`.git` 폴더를 생성해주는 명령어.  처음 한번만 실행한다. 



##### add

working directory 에 있는 파일을 staging area에 올리는 명령어. 



- 기본 사용법
  - file name에 `.` 을 입력하면 모든 파일, 폴더를 한번에 올림

```bash
git add <file name>
```



##### commit

staging area에 있는 파일들을 하나의 commit으로 저장하는 명령어

- 기본사용법
  - `-m` : 커밋 메시지를 작성하기 위한 옵션
  - ``` git commit -m "message"```



##### remote 

원격저장소를 관리하기 위한 명령어

- add : 원격 저장소를 추가

  ```  git remote add <remote name> <URL>
  git remote add <remote name> <URL>
  ```

- remove : 원격 저장소를 제거

  ```bash
  git remote remove <remote name>
  ```



##### push

로컬에 저장되어있는 커밋들을 원격저장소에 업로드 하는 명령어



- 기본 명령어

  ```bash
  git push origin master
  ```

  

##### status

git 의 현재 상태를 확인하는 명령어

- 기본 명령어

  ```bash
  git status
  ```


---------------------------------------------------------------------------------------

##### git 최초 등록시

```bash
git init
git add .
git commit -m "update"
git remote add origin <URL>
git push origin master
```

##### git 업데이트 등록시

```bash 
git add .
git commit -m "update"
git push origin master
```
