# 조건 표현식
***
JavaScript의 특성을 활용해서 
아래의 복잡한 구문을
``` jsx
function SuccessMessageComponent() {
	if(showSuccessMessage) {
		return <div className="successMessage">Authenticated Successful</div>
	}
	return null
}

function ErrorMessageComponent() {
	if(showErrorMessage) {
		return <div className="errorMessage">Authenticated Failed. Please Check your credentials.</div>
	
	}
	return null
}

...
<SuccessMessageComponent />
<ErrorMessageComponent />
```

간단한 조건식으로 사용할 수 있다.

``` jsx
{showSuccessMessage && <div className="successMessage">Authenticated Successful</div>}
{showErrorMessage && <div className="errorMessage">Authenticated Failed. Please Check your credentials.</div>}
```
