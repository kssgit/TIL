# 05. 취소하기

1. git add 취소하기 

   ~~~bash
   $ git status
   On branch main
   Changes to be committed:
     (use "git restore --staged <file>..." to unstage)
           new file:   f.txt
   
   ~~~

   ~~~ bash
   $ git restore --staged f.txt  # 신버젼
   $ git reset HEAD f.txt  # 구버전 (HEAD는 현재 시점)
   ~~~

   ~~~ bash
   $ git status
   On branch main
   Untracked files:
     (use "git add <file>..." to include in what will be committed)
           f.txt
   
   nothing added to commit but untracked files present (use "git add" to track)
   ~~~

2. git commit 취소 (되돌아가기)

   ~~~ bash
   $ git reset (--mixed) [돌아갈 commit 의 hash]
   ~~~

   ~~~
   $ git reset 6463026 
   ~~~

   - 옵션 

     ~~~ bash
     $ git reset --mixed [hash]
     ~~~

     - staging(add한것 까지) 없앱 + **작업한 것( 편집한 코드 파일)은 남아있음 .**
     - 아무것도 입력하지 않으면 이친구 사용?

     ~~~bash
     $ git reset --soft [hash]
     ~~~

     - staging (add 한것은)그대로 유지 + **작업한것은 남아 있음.**

     ~~~ bash
     $ git reset --hard [hash]
     ~~~

     - [주의] **완전히 취소하는 것 (작업한 것도 삭제!!)**

   - hash 

     - ~~~bash
       $ git reset 
       fd30da0719931ca3cc8f64cfef206eb267fbb345 -> 줄인것이 fd30da0
       ~~~

   - HEAD의 상대적 위치 

     - HEAD ~{숫자}

       - HEAD~1 (== HEAD~)
       - HEAD~2

       ~~~bash
       $ git reset (--soft/--mixed) HEAD~
       ~~~

        -  commit 되돌리기 
           	-  HEAD~1(1단계전 commit으로 되돌리고)
               	-  `--mixed`: staging 취소, 작업내용은 유지

   - git log 시 내용이 너무 많이 잘리는 경우 

     - q로 종료
     - 방향키로 위아래 이동 

3. WD(Working Directory)  변경 내용 취소(삭제)하기/ 원상 복구

   - WD 

     -  지금 우리가 작업중인 공간 

     - ==Git이 관리하고 있는 공간(add하고 commit을 한번이라도 한 파일)

     - ==기록이 한번이라도 기록된 파일들이 있는 공간 

       ~~~bash
       $ git status
       On branch main
       Your branch is up to date with 'origin/main'.
       
       Changes not staged for commit:
         (use "git add/rm <file>..." to update what will be committed)
         (use "git restore <file>..." to discard changes in working directory)
               deleted:    a.txt # 커밋되어있는 파일을삭제한경우 
       
       ~~~

   ~~~bash
   $ git restore [파일명]
   $ git restore a.txt
   ~~~

   - 구버전

     ~~~bash
     $ git checkout -- [파일명]
     ~~~

     