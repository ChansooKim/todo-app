# Node.js 주요 명령어
***
`npm start`: **개발 모드**에서 애플리케이션 실행
	개발을 빠르게 변경하고, 브라우저에서 피드백을 볼 수 있게 해줌
	-> npm start로 애플리케이션을 실행하고 코드를 변경하면 npm은 자동으로 앱을 빌드하고 브라우저에 랜더링한다.
	로그로도 확인할 수 있다.
  - Google Chrome 사용 추천

`npm test`: 단위 테스트(Unit Test) 실행

`npm run build`: 프로덕션 환경에 배포 가능한 빌드 생성
	`build` 패키지가 생성된다.
  - 코드 최적화 및 압축(Minified)
  - 성능 최적화(Optimized for performance)

`npm install --save react-router-dom`: 프로젝트에 `react-router-dom` 의존성 추가
	리액트 프로젝트에 종속성을 추가할 떄 사용

