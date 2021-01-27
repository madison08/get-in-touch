<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->

    <touch-button  titleColor=""  btnBackColor="" btnColor="" btnSubmitBackColor="" btnSubmitColor=""/>

  </div>
</template>

<script>
import touchButton from './components/touch-button.vue'

export default {
  name: 'App',
  components: {
    touchButton
  }
}
</script>

<style>
</style>
