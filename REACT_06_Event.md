# Event #

---
<br>

**유저가 웹 브라우저에서 DOM 요소 들과 상호 작용 하는 것을 `이벤트`라고 부른다.**

---
<br>


* ### 이벤트를 사용할때 주의사항 ###
---
 - **이벤트 이름은 카멜클래스로 작성해야한다.**
    <br>
  - **이벤트에 실행할 코드는 함수형태로 전달해야한다.**
<br>
  - **DOM 요소만 가능합니다.`(사용자가 임의로 정의한 컴포넌트는 해당되지않음)`**

---
<br>


+ ## 이벤트 ##
---
+ ### <font color="purple">onChange</font> ###
  - **화살표함수로 구현**
    ```JavaScript
    <input type="text" onChange={(e)=>this.setState({message:e.target.value})}
     value={this.state.input} / >

    ```
    ***<font color="red">화살표함수의 this는 자신을 포함하는  `외부스코프`의 `this`를 계승받는다 그래서 콜백함수로는 용이하다. `객체내에 함수가 정의되어있어야` 객체를 `this`로 가르킴</font>***


    <br>

    **e 는 *`SyntheticEvent`* 객체를 반환하기에 실제적인 변화를 반영하기위해서는 *`e.target.value`* 을 참조하여야 합니다.**
    <br>

    ```JavaScript
      화살표함수(Arrow Function)이란?
      ES6에 새로 도입된 문법으로
      기존의 일반함수가의 this가 "객체" 를 가르킨데에 비해,
      화살표함수는  this가 "인스턴스"를 가르킨다.
    ```
    <br>

  -  **여러개의 컴포넌트제어를 하는 함수**
      ```JavaScript
      handleInputChange(event){
      this.setState({[event.target.name]:event.target.value})
      }
      ```
        + **위의 `[event.target.name]` 은 이벤트가 일어난객체의 name이라는 props를 key로 사용한다는 선언이다.**
---
<br>


+ ### <font color="purple">onKeyPress</font> ###

  ```JavaScript
        handleKeyPress(event){
        if(event.key==='Enter')
          this.pressAlert();
        }
    ```
    <br>

  **코드해설:`SyntheticEvent`객체의 `key`속성을 비교후 함수 실행 _( `SyntheticEvent`객체의 `code`속성을 통해서도 가능)_**
