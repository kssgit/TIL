# 03. Git Remote

- `git remote` : Remote Repository 주소 등록 (여기서는 GitHub Repo)

  - `git remote add origin (주소)`: Remote Repo 주소를 origin 이라는 별칭으로 등록

  - `git reomte -v`:등록된  Remote주소 확인

    - ~~~bash
      origin  https://github.com/Seung-soo-kim/TIL.git (fetch)
      origin  https://github.com/Seung-soo-kim/TIL.git (push)
      ~~~

- `git push (별칭) (브랜치 이름)`: 별칭으로 브랜치를 push(전송)

  - `git push orign main`: origin으로 main브랜치를 전송

- `git clone (주소)`: 주소로부터 Repo 가져오기

- `git pull (별칭) (브랜치 이름)`: 별칭 으로부터 브랜치를 pull(내려받기)