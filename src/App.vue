<template>
  <div id="app">


    <section>
      <Loginpage></Loginpage>
    </section>
  </div>
</template>

<script>
  import Loginpage from './pages/loginpage'

  export default {
    name: 'App',
    components: {
      Loginpage
    }
  }
</script>

<style lang="scss">
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #999999;
  }

  html, body, h1, h2, h3, h4, h5, h6, dl, dd, dt, p, ul, li {
    padding: 0px;
    margin: 0px;
  }

  ul, li {
    list-style: none;
  }
</style>
