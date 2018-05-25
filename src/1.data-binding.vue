<template>
  <div id="app">
    <p>count ：{{count}}</p>
     <input disabled v-bind:value="count">
    <input type="number" v-model="count">
    <p>msg ： {{msg}}</p>
    <input type="text" v-model="msg">
  </div>
</template>

<script>
export default {
  data(){
    return {
      count : 0,
      msg : "Hello Vue"
    }
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
