<template>
  <div id="app">
    <button v-on:click="isShow = !isShow">切り替え</button>
    <div v-if="isShow">
      消えたりかくれたり
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return { 
      isShow : false 
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
