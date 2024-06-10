<template>
  <h1> {{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModel">
    <MyModel :theme="theme" @close="toggleModal">
      <template v-slot:links>
        <a href="#"> Sign up now</a>
        <a href="#"> more info</a>
      </template>
      <h1>Ninja</h1>
    </MyModel>
  </div>

  <div v-if="showModel2">
    <MyModel :theme="theme" @close="toggleModal2">
      <template v-slot:links>
        <a href="#"> Sign up now 2</a>
        <a href="#"> more info 2</a>        
      </template>
      <h1>Second module</h1>
    </MyModel>

  </div>
  


  
  <button @click="toggleModal">Open modal</button> <br>
  <button @click="toggleModal2">Open modal 2</button>
</template>

<script>

import MyModel from './components/MyModel.vue'

export default {
  name:"App",
  components: {MyModel},
  data(){
    return {
      title:"my first new app",
      header: "Sing up for the Giveaway",
      text: "nice text",
      theme: "sale",
      showModel: false,
      showModel2: false
    }
  },
  methods: {
    toggleModal(){
      this.showModel = !this.showModel
    },
    toggleModal2(){
      this.showModel2 = !this.showModel2
    }
  }

}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;

}
</style>
