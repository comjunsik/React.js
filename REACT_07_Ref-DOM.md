# Ref : DOM #
-------

+ **`ref`란 ? HTML에서 tag에 ID를 사용하는 것 처럼 `DOM을 이름을 다는 것` 을 `reference`  라고 합니다.**
    - **<font color="red"> 리액트컴포넌트에서 ID를 사용은 특수한경우가 아니라면 권장하고 있지 않습니다. JSX문법을 렌더링할때 그대로 전달되기 때문에 유일성을 해칠 수 있습니다.</font>**
    <br>
+ **`DOM`을 꼭 직접 건드러야 할때 사용한다.**

    - **<font color="orange">1. 특정 input 에 포커스를 줄 때--_CSS_**
    - **<font color="orange">2. 스크롤 박스를 조작할 시**
    - **<font color="orange">3. Canvas 요소에 그림 그리기를 할 때**  
---
<br>

 ### input에 focus 주기 ###
---

```JavaScript
  onPress(){
    ~ ~ ~ ~
    this.Myinput.focus();
  }
  // onClick 메서드의 콜백함수

  <input ~ ~ ~ ref={(ref)=>{this.Myinput=ref}}>
  //컴포넌트
```

  **코드리뷰 : 텍스트필드의 레퍼런스(객체이름)를 `this.Myinput`이라는 변수에 대입함으로써 `this.Myinput`은 해당 `input`컴포넌트를 가르킴 , 온클릭메서드가 호출 되었을때 `this.input.focus()`를 실행되어 포커싱된다.
  <font color="red"> ref 라는 props는 콜백함수를 받고 함수의 매개변수는 ref를 갖는다</font>**

-----
<br>
### 컴포넌트에 `ref` 달기 ###
---
  + **DOM객체가 아닌 컴포넌트에도 사용이 가능하다.**
      - **컴포넌트(`Scroll Box`)**
      ```JavaScript
        import React from 'react';;

        class ScrollBox extends React.Component{
          render(){
          const style={
            border : '3px solid yellow',
            height: '300px',
            width:'1300px',
            overflow:'auto',  //스크롤바 구현
          position:'relative'
          };

          const innerStyle={
            width:'100%',
            height:'650px',
            background:'linear-gradient(white,yellow)'
            // 박스내의 생상의 그라데이션을 통해
            스크롤바 내용을 잘보기위해서 이런식으로 표현

          }
          return(
            <div style={style} ref={(ref)=>{this.box=ref}}>
            <div style={innerStyle}/>
            </div>
          )
        }
        }export default ScrollBox;


      ```
      - **코드리뷰 :   `background:'linear-gradient(white,yellow)'`
          박스내의 생상의 그라데이션을 통해 스크롤바 내용을 잘보기위해서 이런식으로 표현
          `overflow:'auto'`,  스크롤바 구현을 위한 속성**

  -    ```JavaScript  
          toTop(){
            const{scrollHeight,cilentHeight}=this.box;
            this.box.scrollTop=clientScroll;

        }
        ```
         + **코드리뷰 keyWord 설명
         `scrollHeight`는 전체 문서의 높이
         `clientHeight`는 사용자가 보고있는 높이
         `scrollTop`은 위에 지나간 스크롤의 높이
         `전체길이(scrollHeight)-사용자가 보고있는 높이(clientScroll)`를 하면 `toBottom`
        `지나간 스크롤의 높이(scrollTop)=사용자가 보고있는 높이(clientScroll)`로 하면 `toTop`**
        <br>

        + **위에 사용된 정의를 하는 문법은 비구조화 할당에 해당한다.**
