# JSX #
---
<br>
### 번들링 ###
---

  ``` JavaScript
   var fs = require('fs') 와 import fs from 'fs';
   는 'fs' 모듈을 불러오는 코드 이다 .
   ```
   * **위의 기능은 `Node.js`의 기능 입니다.
   따라서, 웹 브라우저 에서 사용하는 자바스크립트는 `Node.js`   런타임으로 실행하는 것이 아니기 때문에 이 기능을 제공하지 않습니다 .**

   <br>


   + **번들링을 해야 각각의 모듈들을 하나의 파일로 합쳐줌 - `web-pack`의 기능**

  ---
  <br>  


### JSX 란 ? ###
---
+ **이런 식으로 작성된 코드는 번들링 되면서  `Babel-loader`를 통해 `JavaScript` 문법으로 변환 됩니다**
    ```JavaScript
    render(){
      return (
        <div >
          <button onClick={this.props.Clicking.bind(this)} />
        </div>
      );
    }
    ```
    ---

<br>
<br>


### JSX 의 장점 ###
---
+ **가독성이 좋다**
  - `HTML`코드와 비슷하여서 작성또한 쉽다
<br>
+  **오류 검사가 쉽다**
    - `Babel`이 코드를 변환 하는 과정에서 감지해낸다.
    <br>
+ **높은 활용도**

    `<div >` 나 `<span>` 같은 `HTML태그`를 이용할수 있고 ,
    `컴포넌트` 또한 이와 같은 `확장태그`로 작성 가능하다.
---

<br>
### JSX 문법 ###
---
+ **컴포넌트에 여러 요소가 있다면 하나의 부모요소로 감싸야 한다.**
<br>
+ **`Fragment` 컴포넌트는 여러 요소를 랜더링 하기위해 사용한다. 불필요한 `<div>`태그를 대신함**
<br>
+ **JavaScript 문법 사용 가능**
    - `JavaScript expression` 을 사용 하기 위해서는 `{}` 로 감싸면 된다
      <br>
+ **조건부 렌더링을 쉽게 구현할 수 있다**
    - `if 조건문`
    - `삼항연산자`
    - `&& 조건부 렌더링`
<br>
+ **인라인 스타일링**
  - `CSS`스타일을  자바스크립트 객체 형식으로 만들어 적용할 수 있다 .
    - 각각 객체의 키는 `camelCase`로 작성해야한다 .
     `background-color=> backgroundColor`

+ **`class` 대신 `className`**
<br>
+ **태그는 무조건 닫혀야 한다**





---
**추가 기입**
- `const` 은 상수
-  `let` 은 블록단위 지역변수
-  `var` 은 scope단위 **(해당 값을 사용 할 수 있는 코드 영역)** 지역변수


---
<br>
<br>
