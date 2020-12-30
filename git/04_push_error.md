# 04. Push Error

## Pull을 빠트린 경우

- e를 commit

- 그리고 , push

  ~~~ bash
  $ git push origin main
  To https://github.com/kssgit/TIL-test.git
   ! [rejected]        main -> main (fetch first)
  error: failed to push some refs to 'https://github.com/kssgit/TIL-test.git'
  # push 실패
  hint: Updates were rejected because the remote contains work that you do
  #업데이트가 실패했는데, remote(github)가 니가 local(강의장)에 가지고 있지 않은 작업을 들고 있다 여기서는 local에 d.txt가 없다 
  hint: not have locally. This is usually caused by another repository pushing
  # 지금 같은 경우는 다른 Repo로 push하려고 시도한 것이거나
  hint: to the same ref. You may want to first integrate the remote changes
  # push를 다시 하기전에 remote에서 발생한 변경 사항을 먼저 통합(반영)을 해야 할 수 있다.
  hint: (e.g., 'git pull ...') before pushing again.
  hint: See the 'Note about fast-forwards' in 'git push --help' for details.
  ~~~

- `git pull origin main` 할경우

  ~~~ bash
  Merge branch 'main' of https://github.com/kssgit/TIL-test # <- 이미 메세지가 작성되어 있다
  # Please enter a commit message to explain why this merge is necessary,
  #커밋 메시지를 작성해달라 
  # especially if it merges an updated upstream into a topic branch.
  #
  # Lines starting with '#' will be ignored, and an empty message aborts
  # the commit.
  
  ~~~

  - **vim** : 에디터 

    - esc 연타
    - :
    - w(write 저장)
    - q(quit 종료)

  - enter 하면 원래 보던 화면으로 넘어오기 된다 

    ~~~ bash
    $ git pull origin main
    remote: Enumerating objects: 3, done.
    remote: Counting objects: 100% (3/3), done.
    remote: Compressing objects: 100% (1/1), done.
    remote: Total 2 (delta 1), reused 2 (delta 1), pack-reused 0
    Unpacking objects: 100% (2/2), 240 bytes | 20.00 KiB/s, done.
    From https://github.com/kssgit/TIL-test
     * branch            main       -> FETCH_HEAD
       f4e5b8e..b904b82  main       -> origin/main
    Merge made by the 'recursive' strategy.
    # Merge(병합)가 만들어 졌다
     d.txt | 0
     1 file changed, 0 insertions(+), 0 deletions(-)
     create mode 100644 d.txt
    ~~~

    

