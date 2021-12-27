<template>
  <div>
      <img alt="Vue logo" src="./assets/logo.png">
      <form  @submit.prevent="createPost">
        <div>
        <label for="id">Id</label>
        <input type="text" id="id" v-model="formData.id">
        </div>
        <div>
        <label for="title">Id</label>
        <input type="text" id="title" v-model="formData.title">
        </div>
        <div>
        <label for="id">body</label>
        <input type="text" id="body" v-model="formData.body">
        </div>
      </form>
      <button>Add data</button>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'App',
  components: {

  },
  data(){
    return{
      FormData:{
        id:'',
        title:'',
        body:''
      }
    }
  },
  methods:{
    createPost(){
      axios
      .post('https://jsonplaceholder.typicode.com/posts', this.formData)
      .then(response => console.log(response))
      .catch(error => console.log(error))
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
