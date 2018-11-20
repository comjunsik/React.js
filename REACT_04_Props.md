# Props #

  **props 는 부모 컴포넌트가 설정하며 , 컴포넌트 자신은 읽기전용으로만 사용 가능하다**

---
<br>

+ ### JSX 문법에서의 렌더링 ###
---
  - **`{this.props.name}`   형태로 `{}`로 감싸서 표현**
---
<br>

+ ### props 설정 방법 ###
---
  - **`<MyComponent name="" />`**
---
<br>

+ ### props 기본값 설정 ###
---

  - **`MyComponent.defaultProps={name:'홍길동'}`** 과 같은 방식으로 기본값 설정
---
<br>

+ ### props 검증하기  ###
---
  - **`import PropType from 'prop-types'`
    `MyComponent.propTypes={`
      `name:PropTypes.string`
      `age.PropTypes:number.isRequired`
      `}`** 과 같은 방식으로 기본형 설정 및 필수속성 설정
---

  <br>

+ ### prop type 의 종류 ###
---
  |선언|설명|
  |:---:|:---:|
  |**`array`**|**배열**|
  |**`bool`**|**참,거짓**|
  |**`func`**|**함수**|
  |**`number`**|**숫자**|
  |**`object`**|**객체**|
  |**`string`**|**문자열**|
  |**`symbol`**|**심벌객체**|
  |**`node`**|**렌더링가능한 모든 것**|
  |**`element`**|**리액트 요소 **|
  |**`instanceOf(MyClass)`**|**매개변수의 클래스의 인스턴스**|
  |**`oneOf(['Male','Female'])`**|**주어진 배열 요소 중 값 하나**|
  |**`oneofType([React.PropTypes.string,React.PropTypes.number])`**|**주어진 배열안의 종류 중 하나**|
  |**`arrayOf(React.PropTypes.number)`**|**주어진 종류로 구성된 배열--특정 매개변수가 바뀌면 바뀜**|
  |**`objectOf(React.propTypes.number)`**|**주어진 종류의 값을 가진 객체**|
  |**`shape({name: React.PropTypes.string m age:React.PropTypes.number})`**|**주어진 스키마를 가진 객체**|
  |**`any`**|**아무거나 다**|

---
