# `함수형 컴포넌트` #
---
**주로 컴포너트르 만들 때 , React.Component 를 상속한 클래스로 구현 했다고 헀지만,
<font color= "orange"> State  , LifeCycle API</font>를 사용하지않고 , 단순히 <font color ='purple'>props</font>만 사용할 경우 함수형컴포넌트가 더 쉽게 구현할 수 있다.**

---


- ### `함수형컴포넌트의 예` ###
    -
     ``` JavaScript
        import React from 'react'

        function Hello(props)
        {
          return (
            <div>
              Hello{props.name}
            </div>
            )
        }
        export default Hello;

    ```

-  ### `화살표 문법으로 구현` ###

      ``` JavaScript
          import React from 'react'

          const Hello = ({name})=>{
            return(<div>Hell0{name}</div>);
          }


          export default Hello;
      ```
