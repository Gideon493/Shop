<template>
  <!--<img alt="Vue logo" src="./assets/logo.png">-->
  <h2>Online Shop</h2>
  <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
  <shop/>

</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import shop from './components/shop.vue'
//import cart from './components/cart.vue'

export default {
  name: 'App',
  components: {
   
    shop,
    //cart
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
img{
  width:200px;
  
}
</style>
