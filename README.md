#  복습

- GIT은 파일 관리를 총 5가지로 구분한다. 

1. Untracked
  - git이 추적하지 않은 파일
  - 윈도우 기준으로 폴더 내부에 '.git' 폴더가 존재하면 자동으로 추적된다. 
  - '.gitignore'사용을 통해 폴더나 파일을 Untracked상태로 만들 수 있다. 


  2. Tracked
  - git이 변화를 감지하고 있는 상태
  - Tracked 상태는 아래 3가지로 나눌 수 있다.   
    - Unmodified
        - 수정하지 않은 파일(==최신 파일)
        - Local Git에 올라간 파일과 비교했을때, 수정되지 않은 상태

    - Modified(VScode:Changes)
      - 수정한 파일  
    
    - Staged(VScode:Staged Changes)
        - commit을 하기 위해 기다리는 상태 
        - 이 영역을 __staging Area__라고 부름

    

- 명령어 정리 : Local Git Repository

    - 현재 디레토리를 Git 작업 디렉토리로 초기화: git init

    - unmodified -> modified :파일 수정

    - Modified -> staged : git add

    - Staged -> Local Repository : git commit


    - 현재 Git 파일 상태 확인 : git status

    - Git 작업 내역 확인 : git log
        - commit id, 작성자, 날짜, commit message 확인 가능
        - 종료 명령어 : q

    - 명령어 정리 : Remote Git Repository
        - 최초 작업시
            - Local Repo  -> Remote Repo   : git remote add

            - Remote Repo -> Local Repo : git clone



        - 진행 중일 때
            - Local Repo -> Remote Repo : git push

            - Remote Repo -> Local Repo : git pull


     
    



