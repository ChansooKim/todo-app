# 개요
***
기업에서 Full-Stack 아키텍처를 사용하는 이유
- 유연하고 REST API를 사용할 수 있기 때문이다.
	-> 비즈니스 로직을 다시 작성하지 않고도, 모바일 앱과 프론트엔드 애플리케이션, IOT와도 사용할 수 있다.


JavaScript
- ES(`ECMA Script`): JavaScript는 ECMA Script라는 표준 인터페이스를 구현한 것

Node.js 및 npm 설치
https://nodejs.org/en/download

설치 확인
``` cmd
node --version
npm --version
```

###### Node.js
`Node.js` JavaScript의 서버사이드 컴포넌트
	JavaScript 코드를 브라우저 없이 기기에서 바로 실행할 수 있게 해준다.

##### NPM
`npm` JavaScript의 패키지 관리자
	종속성 정보를 특정 파일에 정의하면 npm이 다운로드 해준다.
	Maven, Gradle과 비슷한 역할을 한다.
	`npm init` npm 프로젝트, Node.js 프로젝트를 생성한다.
		`package.json` 파일이 생성되고, 이 파일은 Maven의 `pom.xml`과 유사한 역할을 한다.

`npm install`을 통해 종속성(dependency)를 쉽게 추가할 수 있다.
``` cmd
npm install jquery
```
종속성을 추가하면, `node_modules`라는 폴더가 생성된다.
해당 폴더에 종속성이 다운로드 된다.

`npm`을 이용하면 종속성을 직접 다운로드하고 버전관리를 하지 않아도 된다.
`node_modules`폴더를 삭제해도, `npm install`을 통해 다시 다운로드 할 수 있다.

##### React
`React`: SPA(Single Page Application) 구축에 가장 인기있는 JavaScript 라이브러리 중 하나이다.
	`SPA` 페이지에서 변경되는 부분만 새로고침하는 형태로 애플리케이션을 구축하는 것
	`React`는 페이스북에서 만든 오픈 소스 프로젝트이다.
	컴포넌트의 조합으로 애플리케이션을 만든다. (컴포넌트 기반)
	`React Native`를 통해 안드로이드, iOS 애플리케이션을 만들 수도 있다.

##### React 설치
1. `cd`로 해당 폴더로 이동
	`cd learn-react`
2. `npx create-react-app {app_name}`
	`npx create-react-app todo-app`
	** Mac이나 Linux에 권한 문제가 발생하면, `sudo`를 붙여 사용한다.
		설치가 완료되면 아래와 같은 메시지가 나타난다.
		We suggest that you begin by typing:
		 cd todo-app
		 npm start
		Happy hacking!
3. `cd {app_name}`
4. `npm start`로 리액트 앱을 실행한다.
5. 애플리케이션이 실행되면 브라우저가 나타난다.
** 오류 발생 시
`npm unistall -g create-react-app` create-react-app 삭제
	`-g`: 전역 삭제
`npx clear-npx-cahce` 캐시 삭제
이후 `npx create-react-app`을 통해 재설치

