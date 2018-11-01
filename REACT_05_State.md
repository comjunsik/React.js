# State #


**컴포넌트 내에서 읽고 또 업데이트 할수 있는 값을 사용 가능**

---
<br>


+ ### 컴포넌트 생성자: `constructor()` ###
---
   - **state 초기값은 생성자 내부에 설정**
        * **생성자 메소드는 컴포넌트를 새로 만들 때 실행**
        <br>
        * **생성자 선언**
        ``` JavaScript
            constructor(props){
              super(props);
              this.state={
                name:'이동영',
                age : 26 };
            }
        ```
        * **생성자를 따로 선언하지 않으면 `React.Component`의 생성자를 그대로 사용한다.  거기에 추가 작업을 하기위해서는 생성자를 선언하여 오버라이딩을 한후 , 기존 `React.Component`클래스의 props를 가져오기 위해 `super(props)` 작성후 추가로 필요한 코드 작성**
---

<br>


+ ### state 값 업데이트 : `this.setState()` ###
---
   - **상태멤버변수 업데이트**
  ```JavaScript
    this.setState({
      수정할 필드명1 : 값1 ,
      수정할 필드명2 : 값2 ,})
  ```
  - **`this.state.name=3` 이런식으로 수정을 하게되면 render()함수는 트리거 되지 않는다**
<br>

---
