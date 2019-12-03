<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App" tanggal="7 November 2019"/>
    <p> {{pesan}} </p>
    <p v-if="tampil"> {{pesan}} </p>
    <p v-for="(item,index) in pesan2" :key="index"> {{item}} </p>
    <selamat-datang></selamat-datang>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import SelamatDatang from './components/SelamatDatang.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    SelamatDatang
  },
  data(){
    return{
      pesan: 'selamat sore',
      tampil: false,
      pesan2: ['selamat pagi','selamat siang','selamat malam']
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
