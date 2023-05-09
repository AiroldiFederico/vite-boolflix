<script setup>
import NavBarComp from "./components/NavBarComp.vue"
import MainComp from "./components/MainComp.vue"
import {store} from './store'
import axios from 'axios'
import { onMounted } from 'vue';

const API_KEY = '2ce4dce0e1db39d63e530efad019b36a'

const chiamataApi = () => {
  //Search Movie Database API
  axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${API_KEY}&query=${store.SearchBar}`)
  .then(response => {
      store.MovieFind = response.data.results;
      console.log(store.MovieFind)
      console.log(`https://api.themoviedb.org/3/search/movie?api_key=${API_KEY}&query=${store.SearchBar}`)
  })
}

onMounted(() => {
  chiamataApi()
})


// export default {
//   name: 'app',
//   component: {

//    NavBarComp,
//    MainComp,
//   },

//   data() {
//     return {
//       store,
//       API_KEY: '2ce4dce0e1db39d63e530efad019b36a',
//     }
//   },

//   created() {
//     //this.chiamataApi()
//   },

//   computed: {
//     chiamataApi() {
//       //Search Movie Database API
//       axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.API_KEY}&query=${store.SearchBar}`)
//       .then(response => {
//           this.store.MovieFind = response.data.results;
//           console.log(this.store.MovieFind)
//           console.log(`https://api.themoviedb.org/3/search/movie?api_key=${this.API_KEY}&query=${store.SearchBar}`)
//       })
//     },

//   },

//   methods: {

//   }
// }
</script>



<template>
  <NavBarComp @nomeEmit="chiamataApi()"/>
  <MainComp/>
  
</template>

<style lang="scss">

@use "./style/main.scss" as *;



</style>