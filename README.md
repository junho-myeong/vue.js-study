# vue.js

## Vue.js란?
- vue.js는 javascript freamwork중 하나이다.
- vue는 사용자 인터페이스를 구축하기 위한 javascript프레임 워크이다. 표준 html, css, JS를 기반으로 구축되었으며, 단순한것 부터 복잡한것 까지 사용자의 인터페이스를 효율적으로 개발할수 있는 컴포넌트 기반 프로그래밍 모델을 제공한다.

## CDN,Codepen
- reset css cdn 처럼 cdn방식으로 html에서 script태그를 통해서 외부 사이트에 연결해서 사용할수 잇다.
  ``` html
  <script src="https://unpkg.com/vue@next"></script>
  <div id="app">
    <h1>{{message}}</h1>
    <h2>{{test}}</h2>
  </div>
  ```
  ``` js
  Vue.createApp({
  data() {
    return {
      message: 'Hello Vue!',
      test: 'test!!'
    }
  }
  }).mount('#app')
  ```

## Vue CLI, Vetur
- 설치 방법
  1. npm install -g @vue/cli - 전역 설치를 진행
  1. vue create vue3-test(폴더의 이름) - vue에 관련된 프로젝트폴더 생성하는것이다.
  1. vue cli는 기본적으로 webpack bundler를 사용한다.
  1. vue확장자의 파일은 VScode에서 하이라이팅 되지 않기 때문에 vetur라는 확장 프로그램을 설치해서 사용한다.

## Vue3 Webpack Template
- 우리가 기존에 만들었던 webpack template를 통해서 vue 프로젝트로 만들기
- npx degit junho/webpack-template vue3-webpack-template
- npm i vue@next(vue 패키지를 통해서 vue.js코드를 읽어 들일수만 잇고, 따로 vue라는 확장자를 사용할수잇는 패키지를 설치해 줘야한다.)
- npm i -D vue-loader@next vue-style-loader @vue/compiler-sfc
- webpack.config.js에서 module부분에 vue를 해석할수 잇도록 rules 에 vue확장자를 필터링 해서 vue loader가 실행가능하게 하고
- style부분이 해석 될수 잇도록 scss, css 해석 하게 하는것
- plugin에서 생성자 함수로 끼워 주는것
- npm i -D file-loader(파일을 읽어서 브라우저에 출력해주는 패키지)
- alias를 통해서 별칭으로 파일의 경로를 따져 주고, 그걸로 인해 assets라는 폴더에 접근하기