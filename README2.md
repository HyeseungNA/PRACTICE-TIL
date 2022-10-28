# github 심화


- 작업 단계 되돌리기(작업 취소)

    - working Directory 작업 취소
        - Modified 상태의 파일을 직전 Commint으로 되돌림

        - git restore<파일명>
             - working Directory에서 수정한 파일을 수정 전(직전 커밋)으로 되돌리기
             - 이미 버전 관리가 되고 있는 파일만 되돌리기 가능
             - git restore를 통해 되돌리면, 해당 내용을 복원할 수 없으니 주의할 것!
             - git restore{파일 이름}

    - Staging Area 작업 취소
        - Staged 상태의 파일을 Modified상태로 되돌림(add 취소)
        - root-commit 여부에 따라 두 가지로 나뉨
            - root-commit :이전에 commit을 한 적이 있는 파일이면True
            - root-commit이 없는 경우 : $git rm --cached<파일명>
            - root-commit이 있는 경우: $ git restore--staged<파일명>

    - Repository 작업 취소
        - Commit을 완료한 파일을 Staging Area로 되돌리기( commit 취소 )
        - 명령어 :$git commit --amend
        - staging Area에 다른 파일이 올라와 있는가에 따라서 두 가지로 나뉨
            - Staging Area에 새로 올라온 파일이 없다면 : __직전 Commit의 메시지만 수정__

            - Staging Area에 새로 올라온 내용이 있다면: __직전 커밋을 덮어쓰기__
                - 이 때, Staging Area의 모든 내용이 Commit에 포함된다
        - Commit 메시지 수정을 위해 Vim 편집기가 열림
            - 입력 모드(i): 문서 편집 가능
            - 명령 모드(esc)
                - 명령모드는 ':'과 함께 사용한다. 
                - 저장 후 종료 (:wq)
                - 강제 종료 (:q!)
                    - 리눅스에서 특정 동작을 강제로 수행하게 하는 것 : '!'

    - git reset의 세 가지 옵션
        - --soft
            - 해당 커밋으로 되돌아가고
            - 되돌아간 커밋 이후의 파일들은 Staging Area로 돌려놓음
        - --mixed
            - 해당 커밋으로 되돌아가고
            - 되돌아간 커밋 이우희 파일들은 working Directory로 돌려놓음
            - git reset 옵션의 기본값
        - -- hard
            - 해당 커밋으로 되돌아가고
            - 되돌아간 커밋 이후의 파일들은 모두 Working Directory에서 삭제
                 - 사용 시 주의하기!
            - 기존의 Unteacked 파일은 사라지지 않고 Untracked로 남아있음
    - revert
        - 이전 Commit을 취소하는 역할

        - reset은 커밋 내역을 삭제하지만, revert는 삭제했다는 새로운 커밋을 생성

        - 명령어 :$git revert <commit_id>

            - $git reset<commit_id> : commit_id로 프로젝트를 되돌린다는 뜻
            - $git revert<commit_id>: commit_id에 반영된 내용을 취소한다라는 뜻

            - 여러 내역 revert : $git revert <start_id>..<end_id>
        

