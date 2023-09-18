# 호이스팅과 발생하는 이유에 대해 설명해주세요.
호이스팅이 발생하는 이유는 자바스크립트 엔진은 코드를 실행하기 전 실행 컨텍스트를 생성합니다. 실행 컨텍스트는 생성단계와 실행단계를 거치게 되는데 생성단계에서 코드를 읽기 전 자신의 스코프내에서 선언된 변수와 함수들을 스코프내에 미리 등록시키는 작업이 진행됩니다. 그래서 JS엔진은 코드를 읽기 전 이미 자신의 스코프내에 위치한 변수와 함수들의 존재에 대해 알고 있습니다.

<br/>

⚙️ 용어정리
- 호이스팅 : 변수와 함수 선언은 현재 스코프 맨 위로 끌어올리는 동작
- 실행 컨텍스트 :  JS로 작성된 코드가 실행되기 전 코드가 원활하게 실행될 수 있도록 실행환경을 만들어주는 역할을 함
- TDZ(일시적 사각지대) : 스코프 지삭 지점부터 초기화 시작 지점까지 변수를 참조할 수 없는 구간 => let 키워드로 선언한 변수가 호이스팅이 일어나지 않는 것처럼 보인다. 