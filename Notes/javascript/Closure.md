# 클로저(Closure)에 대해 설명해주세요.
중첩된 함수에서 자식의 함수가 부모의 함수의 변수에 접근할 수 있는 것을 클로저라고 합니다.  
또한 어떤 함수에서 선언한 변수를 참조하는 내부 함수를 외부로 전달할 경우, 함수의 실행 컨텍스트 종료된 후에도 해당 변수가 사라지지 않는 현상도 클로저라 합니다.(함수를 return하는 경우 뿐만 아니라 콜백함수를 전달하는 경우에도 포함)

```js
const outerFunction = () => {
	const a = 10;
	return function(b) {
		console.log(a + b)
	}
}

const getValue = outerFunction()
getValue(20) // 30
```

## 클로저를 사용하는 이유
1. 현재 상태를 기억하고 변경된 최신 상태를 유지하기 위해
2. 전역 변수 사용 억제하기 위해
3. 정보 은닉을 위해

## ⚙️ 용어 정리
- 렉시컬 환경 : 식별자(변수와 함수)와 식별자에 연결된 값 그리고 상위 스코프에 대한 참조를 기록하는 자료구조이다. 이 중 클로저와 가장 연관이 있는 부분은 렉시컬 환경에서 상위 스코프에 대한 참조를 기록하는 곳인 `외부 렉시컬 환경에 대한 참조(Outer Lexical Environment Reference)`이다.
- 실행 컨텍스트 : 자바스크립트가 실행되고 있는 환경을 제공하고 관리하는 곳, 실행 순서와 스코프, 참조에 관한 정보를 갖고 있다.

🔗 참고할 링크
- https://velog.io/@blcklamb/JavaScript-%EA%B8%B0%EC%88%A0%EB%A9%B4%EC%A0%91-%EB%8C%80%EB%B9%84-%ED%81%B4%EB%A1%9C%EC%A0%80-Closure#%ED%81%B4%EB%A1%9C%EC%A0%80%EC%97%90-%EB%8C%80%ED%95%9C-%EC%9D%B4%ED%95%B4