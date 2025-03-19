# React App을 GitHub Repository로 이동
***
``` cmd
git init
git remote add origin https://github.com/{username}/{app_name}
git add .
git commit -m "first commit"
git push -u origin main

Username for 'https://github.com': {username} 
Password for 'https://{username}@github.com': _______
```

1. GitHub에 새로운 Repository를 생성한다.
	1. Repository 명은 react로 생성한 `앱 이름`과 동일하게 하는 것이 좋음
2. git 저장소 초기화 `git init`
3. git 원격 주소 추가 `git remote add origin {github_url}`
4. 스테이지로 모든 변경 사항 이동 `git add .`
5. 변경 사항 커밋 `git commit -m "{commit_message}"`
6. 커밋한 내용 푸시 `git push -u origin main`
7. `username`과 `password` 입력
	1. `username`: GitHub의 사용자명(메인 좌측 상단)
	2. `password`: 일반적으로 github token
8. 완료
		`[new branch]      main -> main`
		`branch 'main' set up to track 'origin/main'.`

[참고](https://velog.io/@a_in/React-Github)


