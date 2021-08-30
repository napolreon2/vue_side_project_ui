<template>
  <div>
    <h1>assets</h1>
    컴파일 되지 않는 폰트, sass, 이미지 등을 넣어두는 resource 성격을 가진 폴더.

    <br>
    <br>
    <hr>

    <h1>pages</h1>
    pages 폴더아래 vue 파일하나하나가 새로운 페이지가 된다. <br>
    route 또한 pages 아래의 경로로 설정된다 <br>

    이 vue 페이지의 경로는 pages/young/young에 있으므로 route는 /young/young이 된다.
    <br>

    정적 페이지 이동방식 => 
    <nuxt-link to="/inspire">Inspire로 이동하기 위한 route : /inspire</nuxt-link>
    
    <br>
    <br>
    <hr>

    <h1>layouts</h1>
    page를 감쌀 layout을 정의. <br>
    layouts 폴더의 default.vue를 보면 내용이 무지하게 많은데 우리는 한가지만 확인하면 된다.

    &lt;nuxt&gt; 라는 태그가 page vue파일들의 내용이 삽입될 곳! 나머지는 레이아웃 폼을 구성하는 태그들!

    <br>
    <br>
    <hr>

    <h1>components</h1>

    vue파일에 import해서 사용할 컴포넌트를 정의 할 수 있다. <br> 
    Vue.js 만 사용할 때와는 다르게 component 폴더아래의 vue파일들은 별도의 import 가 필요없이 자동으로 import된다 <br> 
    -> nuxt.config.js의 components 속성이 true로 되어있기 때문
    <br>
    <br>
    <br>
    <h2>컴포넌트 사용예시</h2>

    <!-- 
      printArea에서 props에 text라는 속성을 정의함
      props는 컴포넌트가 부모로부터 받을수 있는 속성값을 뜻함

      (page인 young은 printArea 라는 컴포넌트를 임포트해서 사용하고 있으므로
      page는 printArea의 부모가 되는 것)

      정의한 속성값에 직접 저렇게 입력을 해주면 자식 컴포넌트는 그 값을 이용할 수 있음
    -->
    <print-area text="내가 입력하면 달라진다"/>
    

    <!--
      위와 같이 직접 입력하는 방식이 아닌, 현재 컴포넌트(혹은 페이지나 레이아웃)의 데이터 값을 연결하고 싶다면
      v-bind 디렉티브를 이용!(tag 안에 속성처럼 사용하는 것을 directive라고 부름)
    -->
    <print-area v-bind:text="pagesText"/>

    <print-area :text="pagesText"/>

  </div>
</template>

<script>
  export default {
    data(){       // data는 함수! 원하는 데이터 json 형태로 리턴해주기!
      return {
        pagesText: '페이지의 텍스트'
      }
    }
  }
</script>

<style>

</style>