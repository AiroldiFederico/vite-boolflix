<script>
    import {store} from '../store'
    //import axios from 'axios'
    export default{
        
        name: "MainComp",
        
        components: {
            
        },

        data(){
            return{
               
               // API_KEY: '2ce4dce0e1db39d63e530efad019b36a',
                store,

            }
        },
        methods: {
            // callApi() {
            //     //Search Movie Database API
            //     axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.API_KEY}&query=${store.SearchBar}`)
            //     .then(response => {
            //         this.store.MovieFind = response.data.results;
            //         console.log(this.store.MovieFind)
            //         console.log(`https://api.themoviedb.org/3/search/movie?api_key=${this.API_KEY}&query=${store.SearchBar}`)
            //     })
            // }

        },

        created() {

        }
    }
    
</script>



<!-- MAIN -->
<template>
    <div id="NameComp" class="bg-dark">


    </div>
</template>





<style lang="scss" scoped>

    div {

        height:calc(100vh - 5.3rem) ;


    }


</style>