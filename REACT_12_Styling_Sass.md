# `Sass` #
---
**`Syntactically Awesome Style Sheet`: 문법적으로 매우 멋진 스타일시트 - 중복되는 코드를 줄여서 보기좋게 작성가능한 스타일 시트.
<a src="https://sass-guidelin.es/ko/" >https://sass-guidelin.es/ko/</a>**

---


 -  **환경설정**

    - ``` JavaScript
        {  // scss 형식의 파일을 번들링하는 설정을 해줌
            test: /\.scss$/,
            use: [
              require.resolve('style-loader'),
              {
                loader: require.resolve('css-loader'),
                options: {
                  modules: true,
                  localIdentName: '[path][name]__[local]--[hash:base64:5]',
                  importLoaders: 1,
                },
              },
              {
                loader: require.resolve('postcss-loader'),
                options: {
                  // Necessary for external CSS imports to work
                  // https://github.com/facebookincubator/create-react-app/issues/2677
                  ident: 'postcss',
                  plugins: () => [
                    require('postcss-flexbugs-fixes'),
                    autoprefixer({
                      browsers: [
                        '>1%',
                        'last 4 versions',
                        'Firefox ESR',
                        'not ie < 9', // React doesn't support IE8 anyway
                      ],
                      flexbox: 'no-2009',
                    }),
                  ],
                },
              },{
                loader:require.resolve('sass-loader'),
                options:{},

              }


    ```


  - ### `App.scss` ###
      - ``` scss
        .box {
          display: inline-block;
          width:100px;
          height:100px;
          border:1px solid black;
          position: fixed;
          top: 50%;
          left:50%;
          transform : translate(-50%,-50%);

          // 각각의 클래스로 구현해야하는 것을 이런형태로 구현가능
          // 클래스내의 클래스 선언
        &.blue{
            background: blue;
          }
          // 마우스가 위로 올라왔을 시
        &:hover {
            background: yellow;
        }
         // 마우스 클릭이 있을 시
        &:active {
          background: red;
        }
        // 클래스내의 클래스라는 것을 가독성 좋게 표현, &가 없으므로 별개의 객체 클래스
        .box-inside{
          background: black;
          width:50px;
          height:50px;
          &:hover{
            background:green;
          }
          //nest 구조도 가능하다.
          //hover 와 active의 구현 순서도 중요하다.
          }
        }
        ```


  - ## `mixin`과 `변수`를 통한 구현 ##
      - ```scss

        $size : 100px;
         //변수로 사용 --- 연산 또한 가능
        @mixin place-at-center(){
          top:50%;
          left:50%;
          transform: translate(-50%,-50%);

        }
        // 자주쓰는 단락 믹스인으로 지정

        .box{
          display: inline-block;
          width:$size;
          height: $size;
          border: 1px black solid;
          position:fixed;

          @include place-at-center();
            // 믹스인 호출

        &.blue
          {
            background: blue;
          }
        &:hover {
          background: yellow;
        }

        &:active{
          background: red;

        }

        .box-inside{
        width:$size/2;
          height: $size/2;
        background: black;
        }
        }
        ```

        -  **`@import './path/A.scss'`로 모듈처럼도 사용가능**
<br>
        - **`config.paths.js`,`webpack.config.dev.js`,`webpack.config.prod.js` 를 수정하여서 하면 PATH를 간소화 할수 있음**


----

## Sass 의 장점 ##
---
 * **스타일관련 라이브러리를 쉽게 불러와 사용이 가능하다.**
     - **`npm`을 통해서 라이브러리 설치후 사용**

<br>

- **`Button.scss`**
 ``` scss
  @import 'src/styles/util';

.button{
    background: $oc-green-7;   //$oc-색-명암
    transition: all .2s ease-in; // 애니메이션 0.2초동안 느린시작으로 진행 - 반응을 여러가지 방법으로 나타낼수있다.
    display: inline-block;
    padding-top: 2rem; //rem은 상위 요소에 따라 반응형으로 변경되어야 할때 사용한다.
    padding-bottom: 2rem; //rem은 상위 요소에 따라 반응형으로 변경되어야 할때 사용한다.
    text-align: center;
    color: white;
    position:fixed;  
    // fixed 메뉴바 같은 곳에 사용 스크롤에 구애받지않고 그자리에 그대로 있음 -- top left 는 %로 나타내야 부자연스럽지 않다.
    // absolute 상위의 요소(static)이 아닌 요소에 따라 상대적으로 움직임
    // relative 자신의 원래위치를 기준으로 움직임

    font-size: 2rem;   //rem은 상위 요소에 따라 반응형으로 변경되어야 할때 사용한다.
    font-weight: 500;
    border-radius:4px;
    cursor:pointer; // 커서 모양

    @include place();
    width:1200px;

    @include media("<huge")
    {
        width:1024px;
    }

    @include media("<large") {
        width: 768px;
    }

    @include media("<medium") {
        width: 90%;
    }

    &:hover{
        background: $oc-green-6;




    }
    &:active{
        margin-top:3px;  //눌렀을 시 버튼이 살 짝 눌리는 느낌이 들게하기 위해
        background: $oc-green-8;
    }

}
```

- **`util.scss`**
```CSS
@import '~open-color/open-color';
@import '~include-media/dist/include-media';

$breakpoints:(
    small:376px,
    medium:768px,
    large:1024px,
    huge:1200px
);
// 인터페이스 , 여기서 설정한 값을 참조하여 이용 한다.


$size: 100px;

@mixin place(){
    top:50%;
    left:50%;
    transform: translate(-50%,-50%);

}

```

#### 주석참고 ####
---
