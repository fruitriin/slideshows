<template>
  <div id="app">
    <button v-on:click="push">増やす</button>
    <button v-on:click="pop">減らす</button>
    <ul>
      <li v-bind:key="item" v-for="(item, key) in lists">
        <input type="text" v-model="lists[key]">
        {{key}} - {{item}}</li>
    </ul>
    <p>{{lists[1]}}</p>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        lists : [1,2,3]
      }
    },
    methods:{
      push(){
        this.lists.push(this.lists.length+1);
      },
      pop(){
        this.lists.pop();
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
