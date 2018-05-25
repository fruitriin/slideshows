<template>
  <div id="app">
    <p>{{user.name}}</p>
    <input v-model="user.name">
    <ul>
      <li v-bind:key="item" v-for="item in user.phoneNumbers">{{item}}</li>
    </ul>
    <ul>
      <li v-bind:key="key" v-for="(item, key) in user.others">{{key}} - {{item}}
      <input v-model="user.others[key]">
      </li>
    </ul>
    <p>{{user.others.hoge}}</p>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        user : {
          name : "test",
          phoneNumbers : [111,222,333],
          others: {
            hoge : "huga",
            foo : "bar"
          }
        },
        newNumber : 111
      }
    },
    methods:{
      push (x){
        this.user.phoneNumbers.push(x);
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
