# Redux에 대해 설명해주세요.
Redux는 리액트에서 사용되는 상태관리 라이브러리 중 하나입니다.  
프로젝트 규모가 커지면 state의 전달이 복잡하고 이는 오류가 발생할 가능성이 높아집니다.
<br/>

리덕스의 주요 개념으로는 action, dispatch, reducer, store가 있고 이러한 순서로 단방향 데이터가 흐르게 됩니다.  
action은 어떤 액션을 취할 것인지 정의해 놓은 객체입니다.  
dispatch는 reducer로 action을 전달해주는 함수입니다.  
reducer는 dispatch에게 전달받은 action객체의 type에 따라 상태를 변경하는 함수입니다.  
store는 redux의 전역 저장소로 redux 앱의 state가 저장되어 있는 오직 하나뿐인 저장소 역할을 합니다.

## 장점
 리덕스 사용시 순수 함수를 사용하기 때문에 상태가 예측 가능하고 유지보수 및 디버깅에 유리하다는 이점이 존재합니다.  


# Redux의 3가지 규칙
1. 하나의 애플리케이션 안에는 하나의 스토어가 존재합니다.
2. 상태는 읽기 전용이다.
3. 변화를 일으키는 함수인 리듀서는 순수한 함수여야 한다.

## 🔗 참고 
- https://lotusstudy.tistory.com/108
- https://lotusstudy.tistory.com/109