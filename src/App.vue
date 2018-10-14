<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <OrderPage/>
  </div>
</template>

<script>   
import OrderPage from './components/OrderPage'
// import OrderPage from './components/Test'

export default {
  name: 'App',
  components: {
    OrderPage
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
