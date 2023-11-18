#  useEffect의 dependency array에 대해서 설명해주세요.
useEffect는 컴포넌트 내에서 side Effect를 실행할 수 있게 하는 Hook입니다. useEffect는 첫번째 인자로 콜백함수를 받고 두 번째 인자로 배열을 받는데 이 배열을 dependency array라고 부릅니다.
useEffect는 화면에 첫 렌더링될 때, 그리고 종속성의 value 값이 바뀔 때마다 실행됩니다. 따라서 모든 state가 아닌 특정 state에 관해
side effect를 실행시킬 수 있습니다.

## ⚙️ 용어 정리
- side effect : 컴포넌트가 화면에 렌더링 된 이후에 비동기로 처리되어야 하는 부수적인 효과들