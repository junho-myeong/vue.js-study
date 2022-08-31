# vue.js

## Vue.js란?
- vue.js는 javascript freamwork중 하나이다.
- vue는 사용자 인터페이스를 구축하기 위한 javascript프레임 워크이다. 표준 html, css, JS를 기반으로 구축되었으며, 단순한것 부터 복잡한것 까지 사용자의 인터페이스를 효율적으로 개발할수 있는 컴포넌트 기반 프로그래밍 모델을 제공한다.

## 설치 방법
프로젝트에 Vue.js를 추가하는 3가지 주요방법이 있습니다.

1. 페이지에 CDN package로 import하기
1. npm 사용하여 import하기
1. 공식 CLI를 사용하여 프로젝트를 scaffold(개발을 용이하게 시작할 수 있는 발판을 제공해줌.)하고, 최신 프론트엔드 워크플로우(예. hot-reload, lint-on-save 등)를 위한 batteries-included build를 제공합니다

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
  1. lint라는 명령어를 통해 우리가 vue를 작성할 규칙을 작성할수 잇다.
  1. vue는 기본적으로 webpack bundler를 사용한다.

## Vue3 Webpack Template
- 우리가 기존에 만들었던 webpack template를 통해서 vue 프로젝트로 만들기
- npx degit junho/webpack-template vue3-webpack-template
- npm i vue@next(vue 패키지를 통해서 vue.js코드를 읽어 들일수만 잇고, 따로 vue라는 확장자를 사용할수잇는 패키지를 설치해 줘야한다.)
- npm i -D vue-loader@next vue-style-loader @vue/compiler-sfc
- entry 포인트 바꿔주기
- webpack.config.js에서 module부분에 vue를 해석할수 잇도록 rules 에 vue확장자를 필터링 해서 vue loader가 실행가능하게 하고
- style부분이 해석 될수 잇도록 scss, css 해석 하게 하는것
- plugin에서 생성자 함수로 끼워 주는것
- import할때 확장자를 따로 작성하지 않아도 되게 해주는것 - webpack.config.js에서 exports 부분에 resolve라는 속성 추가하기
- npm i -D file-loader(파일을 읽어서 브라우저에 출력해주는 패키지)
- alias를 통해서 별칭으로 파일의 경로를 따져 주고, 그걸로 인해 assets라는 폴더에 접근하기

## vue3 Webpack Template-ESLint 구성(vue3-webpack-template)
- eslint란 우리가 vue 코드를 작성할때 사용할 규칙들을 규정하는것이다.
- npm i -D eslint eslint-plugin-vue babel-eslint
- .eslintrc.js 에서 작성된 규칙을 토대로 vue를 작성 할수 잇다.

## 선언적 렌더링과 입력 핸들링(vue3-test1)
- npx degit ParkYoungWoong/vue3-webpack-template#eslint vue3-test1