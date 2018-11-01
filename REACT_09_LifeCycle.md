# Life Cycle #
---
**리액트 컴포넌트는 라이프사이클(수명주기)를 가진다. 렌더링되기 전 준비과정부터 페이지가 사라질 때 끝이 난다.**

---
<br>

---
### 마운트 ###
---
- ### `constructor` ###
    - **생성자 메서드로 컴포넌트를 만들 떄 처음으로 실행된다.**
- ### `getDerivedStateFromProps` ###
    - **props로 받아온 값을 state와 동기화 시키는 용도러 사용한디**
    - ```JavaScript
        static getDerivedStateFromProps(nextProps,prevState)
      ```
- ### `render` ###
    - **컴포넌트 모양을 정의**
    - **this.props,this.state 에 접근가능**
    - **render메서드 내에서는 state의 변형이 일어나서는 안된다.
    <font color="red">DOM정보를 가져오거나 변화를 줄때는 `componentDidMount`애서 처리해야한다.**
- ### `componentDidMount` ###
    - **첫렌더링을 다 마친후 실행한다.**
<br><br>
---
### 업데이트 ###
---
- ### `getDerivedStateFromProps` ###
    - **props가 변경되었거나   부모가 리렌더링되었을시 실행된다.**
- ### `shouldComponentUpdate` ###
    - **props ,state 가 변경되었을시 호출되며 T/F( `리렌더링여부` ) 를 반환한다.**
        + ```JavaScript

              shouldComponentUpdate(nextProps,nextState)
              {
                ...
              return default true;
              }
          ```
- ### `render` ###
    - **위와 같다**
- ### `getSnapshotBeforeUpdate` ###
    - **DOM에 반영하기 바로 직전에  호출하는 메서드이다**
        - ```JavaScript           
            getSnapshotBeforeUpdate(prevProps,prevState)
          {
            ...
            return snapshot;
          }
          ```
- ### `componentDidUpdate` ###
    - **컴포넌트 업데이트 작업(리렌더링)이 끝난후 호출한다.**
    - **업데이트 이전 데이터에 접근가능**
      - ```JavaScript
          componentDidUpdate(prevProps,prevState,
            snapshot )  //getSnapshotBeforeUpdate의 반환값
<br><br>

---

### 언마운트 ###
---
- ### `componentWillUnmount` ###
    - **DOM에서 제거시에 실행**
<br>
<img src="LifeCycle.png"/>
