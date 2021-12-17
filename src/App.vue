<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Header/>
    <Main/>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/macro/Header.vue';
import Main from './components/macro/Main.vue';
import Footer from './components/macro/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
  }
}
</script>

<style lang="scss">
@import './assets/style/global.scss';

</style>
