# React 폴더 구조
***
`README.md` 설명 문서
`package.json` 종속성을 정의하는 파일 (Maven의 `pom.xml`과 유사)
`node_modules` 모든 종속성이 다운로드 되는 폴더
React Initialization(초기화)
	`public/index.html` 브라우저에서 가장 먼저 로드되는 가장 중요한 파일
	`src/index.js` 리액트 앱을 초기화하고 앱 컴포넌트를 로드하는 파일
		여기서 root div (`<div id="root"></div>`)에 접근하고 있고
		그 안에는 앱 컴포넌트가 있다.
		`앱 컴포넌트`: 실제 화면에서 표시되는 컴포넌트
	`src/index.css` 전체 애플리케이션의 스타일을 담고 있는 css 파일
	`src/App.js` 앱 컴포넌트 코드
	`src/App.css` 앱 컴포넌트의 스타일을 담고 있는 css 파일
	`src/App.test.js` 앱 컴포넌트의 단위테스트를 할 때 사용하는 파일
		- Java와 다르게 단위 테스트가 프로덕션 코드와 함께 위치함
	