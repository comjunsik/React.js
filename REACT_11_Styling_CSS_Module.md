#   `CSS Module` #
---
  **컴포넌트 스타일링에 있어서  `CSS`을 사용하여서 처리 합니다.**


---

  - ## `CSS Module` ##
      - **일반적으로는  `web-pack` 의 `css-loader`를 이용하여 일반 `CSS`파일을 불러온다.**
      -  **그러나 클래스 네임이 중복되는 것을 막기 위하여 , 접두사를 붙이곤 한다.**
<br>
      -  **`CSS Module`을 이용하면 고유한 클래스네임을 자동으로 생성하여 , 스코프를 제한한다.**
<br>
      ```JavaScript
        pwd: node_modules/react-script/config/webpack.config.dev.js

        {test : /\.css $/,
         use:[
           require.resolve('style-loader'),
           {
             loader: require.resolve{'css-loader'),  
                // css-loader 은 css 파일에서 import url문을 webpack 의 require(번들링과정)으로 처리하는 역활을 수행한다.  

             options : {
               importLoaders: 1,

               modules : true,
               // css모듈을 활성화 한다.

               localIdentName:'[path][name]__[local]--[hash:base64:5]'
               // 고유하게 생성되는 클래스네임의 형식을 지정해주는 구간이다.

             },
           },
           {
             loader: require.resolve('postcss-loader'),
             // 모든 브라우저에서 작동할수 있게 -webkit, -mos 등 접두사를 붙여준다.
             options:{
               .....
             }
           }
         ]}
      ```
    - **<font color='purple'> `webpack.config.prod.js` 은 배포시에는 꼭 수정해주어야 한다.</font>**
<br>
    - **ClassNames 라이브러리를 통한 편리한 CSS구현**

        -
        ``` JavaScript
        import React from 'react';
        import ClassNames from 'classnames/bind';
        import styles from './App.css'

        const cx = classNames.bind(styles);

        class App extends React.Component{
          render(){
            return(
              <div className={cx('box','blue')} / >

            );
          }
        }
        export default App;
      ```

    - **동적프로그래밍을 위한 구현**

      - ```JavaScript
        import React from 'react';
        import ClassNames from 'classnames/bind';
        import styles from './App.css'

        const cx = classNames.bind(styles);

        class App extends React.Component{
          render(){
            const isBlue=true;

            return(
              <div className={cx('box',{blue: isBlue})} / >

            );
          }
        }
        export default App;
