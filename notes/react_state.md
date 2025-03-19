# State
***
##### State란
- React 내장 객체로, 컴포넌트의 데이터나 정보를 저장하는 데 사용됨

- 초기 React 버전에서 State 관리
	- 초기 버전에서는 클래스 컴포넌트(Class Components)에서만 state를 사용할 수 있었다.
	- 그리고 state를 구현하는 것이 매우 복잡했다.

###### React 16.8에서 Hooks 도입
- Hooks는 사용하기 쉽다.
- `useState` Hook을 사용하면 함수형 컴포넌트에서도 state를 추가할 수 있다.
	- `useState`는 두 가지 값을 반환한다
    1. 현재 상태 (Current state)
    2. 상태를 업데이트하는 함수 (Function to update state)
- 각 컴포넌트 인스턴스는 독립적인 state를 가짐

###### 컴포넌트 간 state를 공유하는 방법
- state를 "위로 올려서"(upwards) 부모 컴포넌트에서 관리

``` jsx
import { useState } from 'react';
import './Counter.css'

export default function Counter() {
    const [count, setCount] = useState(0);

    function incrementCounterFuntion() {
        setCount(count+1)
    }

    function decrementCounterFunction() {
        setCount(count-1)
    }

    return (
        <div className="Counter">
            <span className="count">{count}</span>
            <div>
                <button className="counterButton"
                        onClick={incrementCounterFuntion}
                >+1</button>
                <button className="counterButton"
                        onClick={decrementCounterFunction}
                >-1</button>
            </div>
        </div>
    )
}
```

##### State의 원리

`State`를 업데이트하면 React가 뷰를 업데이트한다.
	HTML Element의 업데이트 원리
	- HTML 페이지는 DOM(Document Object Model)으로 표현된다.
	- HTML 페이지의 각 요소는 DOM의 노드(Node)이다.
	- 요소를 업데이트하려면 DOM을 업데이트해야 한다.
	- 하지만 DOM을 직접 업데이트하는 코드는 복잡하고 느릴 수 있다
=>
React는 다른 접근 방식을 사용함
`Virtual DOM`을 사용한다("가상" UI 표현)
- React 코드가 Virtual DOM을 업데이트
- React는 변경 사항을 감지하고 이를 HTML 페이지와 동기화
1. React는 초기 로드 시 Virtual DOM v1 생성
2. 사용자가 액션을 수행
3. React는 사용자 액션을 기반으로 Virtual DOM v2 생성
4. React는 v1과 v2를 비교(diff 연산 수행)
5. React가 변경 사항을 HTML 페이지에 반영 (동기화)

요약
- 우리는 DOM을 직접 업데이트하지 않는다.
- React는 변경 사항을 감지하고 더 효율적으로 DOM을 업데이트
	- 컴포넌트의 상태가 조금이라도 변경되면 React는 Virtual DOM부터 업데이트한다.