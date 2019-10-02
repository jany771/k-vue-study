<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <hello message="hello jany" foo="kkkk" ref='hi'></hello>
    <slots></slots> -->
    <!-- 通信 -->
    <!-- <communicate></communicate> -->
  <k-form></k-form>
  </div>
</template>

<script>

import Hello from './components/Hello.vue'
import Slots from './components/slots'
import Communicate from './components/communicate'
import KForm from './components/kForm'

export default {
  name: 'app',
  components: {
    Hello,
    Slots,
    Communicate,
    KForm

  },
  data () {
    return {
      message:"zhuzhu"
    }
  },
  mounted () {
    //通过父元素改变子元素的内容
    //this.$refs.hi.name = "EY";
    this.$children[0].name = "伊娃"
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
