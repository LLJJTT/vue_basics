<template>
  <div id="app">
    <!-- <test msg="这是更改后的内容"></test> -->
    <users></users>
  </div>
</template>

<script>
// 通常不写分号
import Test from './components/test'
import Users from './components/users'
export default {
  name: 'app',
  components: {

    Test,Users
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
