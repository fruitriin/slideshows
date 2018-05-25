<template>
  <div id="app">
    <p>count ：{{count}}</p>
    <input type="number" v-model="count">
    <p>
      <button v-on:click="increment">+1</button>
      <button v-on:click="increments(5)">+5</button>
    </p>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        count : 0
      }
    },
    methods : {
      increment(){
        this.count++;
      },
      increments(x = 1){
        this.count += x;
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
