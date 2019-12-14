<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <UserCard v-if="user" :user="user"></UserCard>
  </div>
  
</template>

<script>
import UserCard from './components/UserCard.vue'
import axios from 'axios'
export default {
  name: 'app',
  components: {
    UserCard
  },
  data(){
    return{
      user: null
    }
  },
    mounted(){

      this.axios.get('https://randomuser.me/api/').then((response) => {
        this.user = response.data.results[0]
        console.log('SUCCESSS', response);
      })
      .catch((error) => {
        console.log(error);
      })
      .then(() => {

      })
      console.log('privet');
    }

  }
</script>

<style>

</style>
