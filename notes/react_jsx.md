# JSX
***
대부분의 리액트 프로젝트는 보여지는 것(presentation)을 `JSX`로 한다.
###### `JSX` JavaScript XML
- JavaScript XML은 HTML보다 엄격하다.
	1. 닫는 태그 필수 (`<Component/>` 사용 가능)
	2. 최상위 태그는 하나만 가능
		- 여러 개의 최상위 태그가 있을 수 없다.
		- 공유 부모로 묶어줘야 한다.
			`<div>...</div> or <>...</>(empty wrpper)`

각 컴포넌트는 JSX를 반환하고, 앱 컴포넌트에 담겨있는 것도 JSX이다.

리액트 프로젝트에서 JSX가 활성화되는 원리
- 브라우저마다 최신 기능에 대한 지원 수준이 다르다.
	-> JavaScript 코드에 대한 호환성 보장을 `Babel`로 한다.
		Babel은 모던 자바스크립트로 코드를 작성해도 옛날 브라우저에서 실행될 수 있도록 해준다. (Babel은 JSX를 지원한다)

###### `Babel` JavaScript 컴파일러
https://babeljs.io/
- 브라우저마다 최신 기능에 대한 지원 수준이 다르다.
	-> JavaScript 코드에 대한 호환성 보장을 `Babel`로 한다.
		Babel은 모던 자바스크립트로 코드를 작성해도 옛날 브라우저에서 실행될 수 있도록 해준다. (Babel은 JSX를 지원한다)
- Babel은 JSX를 JS로 변환한다.
``` jsx
<h1 className="something" attr="10">heading</h1>
```
-> (Try it out)
``` js
import { jsx as _jsx } from "react/jsx-runtime";
/*#__PURE__*/_jsx("h1", {
  className: "something",
  attr: "10",
  children: "heading"
});
```

##### JSX 사용법
- 괄호 ()를 사용하면 복잡한 JSX 값을 반환하기 쉬워짐
- 사용자 정의 컴포넌트(Custom Components)는 대문자로 시작해야 함
- HTML 태그는 소문자로 작성해야 함
- CSS 클래스 지정 - className 사용
	- HTML의 class 속성과 유사
	  (CSS와 HTML에서는 `class`를 사용하지만, JSX에서는 `className`이 권장됨)
``` jsx
function App() {
	return (
		<div className="App">
			<FirstComponent/>
			<SecondComponent></SecondComponent>
			<ThirdComponent></ThirdComponent>
			<FourthComponent></FourthComponent>
		</div>
	);
}
```
=> 이 때, className으로 정의된 `App`은 `App.css`의 css 스타일이 적용된다.

`export default`를 사용해서 `FirstComponent.jsx`파일을 생성한다.
``` jsx
export default function FirstComponent(){
	return (
		<div className='FirstComponent'>First Component</div>
	)
}
```

** 컴포넌트를 정의(import)할 때 중괄호를 쓰지 않으면 나오는 것은 무조건 기본 컴포넌트이다. (`export default`를 통해 정의된)

``` jsx
import FirstComponent from './components/learning-examples/FirstComponent';
import { FifthComponent } from './components/learning-examples/FirstComponent';
```

아래와 같이 `FirstComponent.jsx`파일 내부에 `FifthComponent`라는 함수 컴포넌트가 정의되어 있다면, 반드시 중괄호`{ ... }`를 통해 컴포넌트를 Import 해야 한다.
	-> 중괄호가 이 컴포넌트가 default가 아니라는 것을 알려준다.
``` jsx
export default function FirstComponent() {
	return (
		<div className='FirstComponent'>First Component</div>
	)
}

export function FifthComponent() {
	return (
		<div className='FifthComponent'>Fifth Component</div>
	)
}
```

-> 반대로 실제 존재하지 않는 아무 이름이나 import를 해도 소스코드는 문제가 없고, `export default`로 정의된 컴포넌트가 추가된다.
`import TenthComponent from './components/learning-examples/FirstComponent';`

##### JavaScript 모듈화 (모범 사례)
***
**각 컴포넌트는 개별 파일(또는 모듈)로 분리**
- 다른 모듈의 클래스를 사용하려면 import 필요
	- 기본(Default) import
    ```javascript
    import FirstComponent from './components/learning/FirstComponent.jsx';
    ```
	- 이름(Named) import
    ```javascript
    import { FirstComponent } from './components/learning/FirstComponent.jsx';
    ```

이런 식으로 컴포넌트를 개별 파일로 분리 (모듈화) 하는것을 추천한다.
``` jsx
import './App.css';
import FirstComponent from './components/learning-examples/FirstComponent';
import SecondComponent from './components/learning-examples/SecondComponent';
import ThirdComponent from './components/learning-examples/ThirdComponent';
import FourthComponent from './components/learning-examples/FourthComponent';

function App() {
	return (
	<div className="App">
		<FirstComponent/>
		<SecondComponent></SecondComponent>
		<ThirdComponent></ThirdComponent>
		<FourthComponent></FourthComponent>
	</div>
	);
}

export default App;
```
-> 여러 가지의 컴포넌트가 사용된 다면 이 또한 모듈화를 하는 것이 좋다.

=>
``` jsx
import './App.css';
import LearningComponent from './components/learning-examples/LearningComponent';

function App() {
	return (
		<div className="App">
			<LearningComponent/>
		</div>
	);
}

export default App;
```

``` jsx
import FirstComponent from './FirstComponent';
import { FifthComponent } from './FirstComponent';
import SecondComponent from './SecondComponent';
import ThirdComponent from './ThirdComponent';
import FourthComponent from './FourthComponent';

export default function LearningComponent() {
	return (
	<div className="App">
		<FirstComponent/>
		<SecondComponent></SecondComponent>
		<ThirdComponent></ThirdComponent>
		<FourthComponent></FourthComponent>
		<FifthComponent></FifthComponent>
	</div>
	);
}
```


##### JavaScript의 특징
- 세미콜론(`;`)을 사용할 필요 없음
- 동적 객체 (Dynamic objects)
- 객체에 함수를 저장할 수 있음

``` jsx
const person = {
    name: 'Ranga Karanam',
    address: {
        line1: 'Baker Street',
        city: 'London',
        country: 'UK'
    },
    profiles: ['twitter', 'linkedin', 'instagram'],
    printProfile: () => {
        person.profiles.map(
            profile => console.log(profile)
        )
    }
}

export default function LearningJavaScript() {
    return (
        <>
            <div>{person.name}</div>
            <div>{person.address.line1}</div>
            <div>{person.profiles[0]}</div>
            <div>{person.printProfile()}</div>
        </>
    )
}
```