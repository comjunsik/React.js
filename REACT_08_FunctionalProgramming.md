# Functional Programming #
---
**컴포넌트 생성시 반복되는 코드를 함수형 프로그래밍으로 짜면 매우 편리하다.
`map`,`filter`,`reduce` 함수가 대표적이다**

<br>

---

+ **<font color="orange">수정전</font>**
 ```JavaScript
       render(){
         return(
           <ul>
           <li>눈사람</li>
           <li>얼음</li>
           <li>눈</li>
           <li>바람</li>
           </ul>
           )
       }
 ```

+ **<font color="red">함수형 프로그래밍으로 수정후</font>**
  ```JavaScript
    render(){
      let tag=List.map((list)=>((<li>{list}</li>))
      return(
        <ul>
        {tag}
        </ul>
      )
    }
  ```
    - **위의 List 클래스내에 선언된 위와 같은 배열이다**


---

### 전개연산자 ###

---
**객체를 복사하거나 배열에서 이후의 값을 복사할때 사용하곤 한다, 배열을 합치기에도 용이하다**
  ```JavaScript
    const number=[1,2,3,4,5]
    const number=[...number,6,7] // [1,2,3,4,5,6,7]
