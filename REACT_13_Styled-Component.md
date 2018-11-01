# `Styled Components` #
---
**`CSS in JS`의 형태로 구현된 컴포넌트**

---

  - ### dev setting ###
    - **`npm add styled-components`** 을 통해 라이브러리 설치
<br>

  - ### 코드의 예시 ###
    ```JavaScript
    path: src/StyledButton.js

    import React from 'react';
    import styled from 'styled-components';

    const Wrapper = styled.dev`
    display: inline-block;
    border : black 1px solid;
    border-radius : 3px;
    padding : 1rem;

    // 마우스가 위치 하였을 때

    &:hover{
      background:black;
      color:white; // 글자색

    };
    `

    const StyledButton=({children , ...rest})=>{return(<
      Wrapper {...rest}>{children}</Wrapper>)
    }

    export default StyledButton;

    // styled-components 라이브러리의 styled를 사용하여 styling 이 된 div를 Wrapper 컴포넌트로 사용하게 선언
    // children 은 태그내부에 선언된 코드
    // ..rest 는 컴포넌트가 받은 props

    ```
    - **`Tagged Template Literal` 문법**
        - ```JavaScript
          back-quioton(`) 으로 문자열을 감싸고 문자열 내의
          value 는 ${expression} 으로 표현한다.

          ```


- ### `props`를 받아 사용하는 동적인 컴포넌트 만들기 ###
    -  ``` JavaScript
        import React from 'react';
        import styled from 'styled-components';

        const Wrapper =styled.div`
        display:inline-block;
        border: solid black 1px;
        border-radius: 3px;
        padding : 1rem;

        font-size:${props=>props.fontSize};
        ${props=>props.big&&`font-size:2rem;
          padding : 2rem`
        }
        &:hover{
          background:back;
          color:white;
        }
        `
        const StyledButton =({children,big,...rest})=>{
          return(
            <Wrapper big={big} fontSize="1.25rem" {...rest}>
            {children}
            </Wrapper>
            )
        }
        export default StyledButton;
        ```


        - **&&논리연산자롤 통한 값 지정**



<br>


  -  **자바스크립트에서의 논리연산**

      ```
      자바스크립트의 ||, && 연산자는 불린값을 리턴하지 않는다. 값 자체를 리턴한다.

      따라서 값의 성질(true, false)에 따라 앞의 값이 출력되던지, 뒤의 값이 출력되던지 한다.



      or의 경우, 둘 중 하나만 true면 true를 반환하니까 만약 앞의 값이 false라면 뒤의 값을 리턴한다.

      뒤의 값이 true라면 true가 나오는 것이고, false면 false가 나올 테니까.

        물론 앞의 값이 true라면 뒤의 값을 볼 필요도 없이 앞의 값을 리턴한다.



        and의 경우는 or과 반대다. 둘 중 하나만 false면 false를 반환하니까 만약 앞의 값이 true라면 뒤의 값을 리턴한다. 마찬가지로 앞의 값이 false면 그냥 앞의 값을 리턴한다.



        중요한 점은, 첫줄에서도 강조했듯이 불린값을 리턴하는게 아니라 값 자체를 리턴한다는 점이다.
    ```


    -  **false로 취급되는 값**


        - `false`
        - `""`
        - `null`
        - `undefined`
        - `0`
        - `NaN`

        **위 값들을 제외하고 나머지 값들은, Javascript 언어의 조건식(conditional expression)에  서, true로 취급한다.**
