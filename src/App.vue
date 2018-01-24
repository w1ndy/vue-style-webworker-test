<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import { SOME_CONSTANT } from './assets/test.scss'
import TestWorker from 'worker-loader!./assets/test.worker.js'

export default {
  name: 'App',
  mounted () {
    console.log('The value of the constant is', SOME_CONSTANT)
  },
  data () {
    return {
      worker: new TestWorker()
    }
  },
  components: {
    HelloWorld
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
