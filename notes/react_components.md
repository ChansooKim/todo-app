# React 컴포넌트
***
> React 컴포넌트가 필요한 이유

웹 애플리케이션은 복잡한 구조를 가진다.
- 메뉴(Menu), 헤더(Header), 푸터(Footer), 웰컴 페이지(Welcome Page), 로그인 페이지(Login Page), 로그아웃 페이지(Logout Page), 투두 페이지(Todo Page) 등 다양한 요소 포함

컴포넌트(Components)는 React 앱을 모듈화(Modularization)하는 데 도움을 준다.
- 각 페이지 요소에 대해 개별 컴포넌트 생성 (Create separate components)
	메뉴 컴포넌트(Menu Component)
	헤더 컴포넌트(Header Component)
	푸터 컴포넌트(Footer Component)
	…
- 필요한 이유
  - 모듈화(Modularization)
  - 재사용(Reuse)

##### React 컴포넌트
***
- React 앱에서 가장 먼저 로드되는 컴포넌트: **`App` 컴포넌트**

###### 컴포넌트 구성 요소
- `View`: JSX 또는 JavaScript 기반의 UI
- `Logic`: JavaScript 코드로 구성된 로직
- `Styling`: CSS를 이용한 스타일링
- `State`: 내부 데이터 저장소 (Internal Data Store)
- `Props`: 데이터 전달 (Pass Data)

** React 컴포넌트의 작성 규칙
- React 컴포넌트의 이름은 항상 `대문자로 시작`해야 한다.
- 모든 컴포넌트에서 뭘 가지고 있든 `괄호 안에` 넣는다.

**사용 방법**
###### `함수 컴포넌트`
``` js
function FirstComponent() {
	return (
		<div className='FirstComponent'>First Component</div>
	)
}
```
Component를 정의한 후
-> 이것을 `함수 컴포넌트`라고 부른다.

``` js
function App() {
	return (
		<div className="App">
			My Todo Application Updated
			<FirstComponent></FirstComponent>
		</div>
	);
}
```
`<{Component_Name}></{Component_Name}>`으로 사용한다.

###### `클래스 컴포넌트`
``` js
import {Component} from 'react';
...
class ThirdComponent extends Component{
	render() {
		return (
			<div className='ThirdComponent'>Third Component</div>
		)
	}
}
```
랜더링 메서드는 컴포넌트 일부로 보여주고 싶은 텍스트를 반환해야 한다.

##### `State`
특정 컴포넌트에 대한 데이터나 정보
	리액트 초기 버전에서는 클래스 컴포넌트만 `State`를 가질 수 있었다.
	-> 함수 컴포넌트에는 `State`가 없다.
	하지만, `React 16.8 버전`부터 `Hooks`이라는 새로운 개념이 소개되었다.
	-> `Hooks`는 함수 컴포넌트에도 `State`를 추가할 수 있게 해준다.
	.
	따라서, React 17,18,19.. 등을 사용한다면 거의 다 함수 컴포넌트를 사용해서 애플리케이션을 만드는 것을 볼 수 있다. (클래스 컴포넌트를 사용할 필요가 없다)


##### 컴포넌트의 구성 요소 (Parts of a Component)
- View (JSX 또는 JavaScript)
- Logic (JavaScript)
- Styling (CSS)
- State (내부 데이터 저장소)
- Props (데이터 전달)

###### 컴포넌트 스타일링 옵션
1. style 속성 사용
   요소 안에서 하드코딩
   -> 반드시 중괄호를 이중으로 사용, '-' 대신 camelCase로 정의
``` js
<button style={border-radius:30px}>  -- X
<button style={{borderRadius:"30px"}}> -- O
```
2. 컴포넌트의 CSS 파일에서 cssClass 정의
``` css
.count {
	font-size: 150px;
	padding: 20px;
}
```
