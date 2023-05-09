<script>
    import {store} from '../store'

    export default{
        
        name: "CardFilmComp",
        
        components: {
            
        },

        data(){
            return{
               
                store,

            }
        },

    }
    
</script>



<!-- CARD -->
<template>
    <div>
        <div class="card" style="width: 18rem;" v-for="(object, index) in store.MovieFind" key="index">
            <img :src="`https://image.tmdb.org/t/p/w342${store.MovieFind[index].backdrop_path}`" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">{{store.MovieFind[index].title}}</h5>
              <!-- <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p> -->
            </div>
            <ul class="list-group list-group-flush">
              <li class="list-group-item">{{store.MovieFind[index].original_title}}</li>
              <li class="list-group-item">Lingua: {{store.MovieFind[index].original_language}}</li>
              <li class="list-group-item">Voto: {{store.MovieFind[index].vote_average}}</li>
            </ul>
        </div>
    </div>
</template>





<style lang="scss" scoped>

div {
    display: flex;
    flex-wrap: wrap;
    margin-bottom: 1rem;
    gap: 0.8rem;
    justify-content: space-start;
}



</style>