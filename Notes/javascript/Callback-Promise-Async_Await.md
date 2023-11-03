# 콜백 함수에 대해 설명해주세요.
다른 함수가 실행을 끝낸 뒤 실행되는 함수를 말합니다.
즉, 코드를 통해 명시적으로 호출하는 함수가 아니라 함수를 등록해놓은 후 어떤 이벤트가 발생했거나 특정 시점에 도달했을 때 시스템에서 호출하는 함수를 말합니다.

<a href="https://youtu.be/8aGhZQkoFbQ" target="_blank">🔗 참고할 영상</a>

<br/>

## 콜백 지옥을 해결하는 방법을 설명해주세요.
콜백 지옥은 비동기 처리 로직을 위해 콜백 함수를 연속해서 사용할 때 발생하는 문제입니다. 이것을 해결하기 위해 Promise, async/await을 사용하는 방법이 있습니다.

<br/>

# Promise에 대해 설명해주세요.
자바스크립트에서 제공하는 비동기 처리를 위한 객체입니다. 정해진 기능을 수행하고 나서 수행이 성공했다면 성공의 메세지를, 기능을 수행하다 예상치 못한 에러가 생기면 에러를 표출할 수 있도록 도와줍니다. 즉 Promise란, 실행은 바로 하되, 결과값을 나중에 원할 때 쓸 수 있는 것입니다.

```js
const promise = new Promise((resolve, reject) => {
	// 비동기 작업 성공시 resolve()를 호출하고,
  	// 비동기 작업 실패시 reject()를 호출하도록 한다.
})
```
```js
promise.then( (data) => {
	return new Promise((resolve, reject) => {
    	// 처리 내용
    }). then((data2) => {
    	// 처리 내용
    }).catch(
    	console.log(ErrorMessage)
    )
})
.catch(
	console.log(ErrorMessage)
)
```
<br/>

## Promise.all() 에 대해 설명해주세요.
여러 개의 Promise들을 배열 인자로 받아서 그 객체들을 순회하면서 비동기 작업들을 처리합니다. 입력값으로 들어온 Promise 중 하나라도 거부 당하면 Promise.all()도 즉시 거부됩니다.

```js
Promise.all([
  new Promise((resolve, reject) => setTimeout(() => resolve(1), 1000)),
  new Promise((resolve, reject) => setTimeout(() => reject(new Error("에러 발생!")), 2000)),
  new Promise((resolve, reject) => setTimeout(() => resolve(3), 3000))
]).catch(alert); // Error: 에러 발생!
```

<br/>

# Promise와 Callback를 비교 설명해주세요.
콜백함수는 비동기 로직의 결과값을 처리하기 위해서 callback 안에서만 처리를 해야하고, 콜백 밖에서는 비동기에서 온 값을 알 수가 없습니다.  
반면, 프로미스를 사용하면 비동기에서 온 값이 프로미스 객체에 저장되기 때문에 코드 작성이 용이해집니다.

<br/>

# Async, Await이 뭔지 그리고 사용 방법을 설명해주세요.
기존의 비동기 처리 방식인 콜백함수의 단점을 보완하기 위해 Promise를 사용했지만, 코드가 장황하다는 단점이 있었습니다. 이를 해결하기 위해 ES8에서 Async, Await이 도입되었습니다. Async, Await은 Promise를 반환합니다.
```js
async function 함수명(){
	await 비동기_처리_메소드_이름()
}
```
```js
function delay(ms){
	return new Promise(resolve => setTimeout(resolve, ms));
}

async function getApple(){
	await delay(2000)
  return "Apple"
}

async function getBanana(){
	await delay(1000)
  return "Banana"
}

getApple().then((data) => console.log(data)) //'Apple'
getBanana().then((data) => console.log(data)) //'Banana'
```

<br/>

# Async, Await을 사용했을 때의 장점을 설명해주세요.
1. 가독성이 좋습니다.
2. 에러 처리가 간편해집니다. try/catch 문을 통해 동기 코드와 같은 방식으로 에러를 처리할 수 있습니다.

# Async, Await을 사용했을 때의 단점을 설명해주세요.
무조건 Promise만 반환합니다. 반환 값을 직접 사용하려면 추가적인 처리가 필요합니다.

<br/>

# Promise와 Async, Await의 차이를 설명해주세요.
Promise 를 활용할 시에는 .catch() 문을 통해 에러 핸들링이 가능하지만, async/await 은 에러 핸들링 할 수 있는 기능이 없어 try-catch() 문을 활용해야 합니다. 또, Promise는 then() 지옥에 빠질 수 있지만, Async/Await은 비동기 코드를 동기 코드처럼 읽히게 코드 흐름을 이해하기 쉽습니다.