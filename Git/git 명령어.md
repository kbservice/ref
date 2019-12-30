# Git 명령어

## git config : 설정

- `--local` 설정 : `.git/config` 파일에 저장 - **기본값**
- `--global` 설정 : `~/.gitconfig` 파일에 저장
- `--system` 설정 : `/etc/gitconfig` 파일에 저장

- `--list`, `-l` : 설정값 출력

- `user.name` : 사용자명
- `user.email` : 사용자 이메일

### git status : 상태확인

- git 현재 상태 확인하기

### git add : tracked -> staging area 

- `.`
- `*`

### git commit

- `-m [메시지]` : 커밋 메시지
- `-a` : `git add` 와 동일, tracked -> staging area로 올리기
