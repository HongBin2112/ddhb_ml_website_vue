<template>
  <div>
    <Header></Header>
    <hr>
    <IntroBlock></IntroBlock>
    <hr>
    <MoreArticles></MoreArticles>
    <hr>
    <Footer></Footer>
  </div>
</template>

<script>
  //import HelloWorld from './components/HelloWorld.vue'
  import Header from './components/Header.vue';
  import Footer from './components/Footer.vue';
  import IntroBlock from './components/IntroBlock.vue';
  import MoreArticles from './components/MoreArticles.vue';

  export default {
    name: 'App',
    components: {
      Header,
      Footer,
      IntroBlock,
      MoreArticles
    }
  }
</script>

<style>

@import url(https://fonts.googleapis.com/earlyaccess/cwtexyen.css); /* 下載字型 */

  #app {
    font-family: 'Noto Sans TC',sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;

    margin-top: 0px;
    background-color:azure;
  }
</style>
