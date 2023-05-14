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

        <h2>MOVIE</h2>
        <div class="card-container">
            <div  v-for="(object, index) in store.MovieFind" key="index">
                <div class="card" style="width: 18rem;">
                    <img :src="`https://image.tmdb.org/t/p/w342${store.MovieFind[index].poster_path}`" class="card-img-top" alt="...">
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
        </div>


        <h2>SERIES TV</h2>
        <div class="card-container">
            <div  v-for="(object, index) in store.SerieFind" key="index">
                <div class="card" style="width: 18rem;">
                    <img :src="`https://image.tmdb.org/t/p/w342${store.SerieFind[index].poster_path}`" class="card-img-top" alt="...">
                    <div class="card-body">
                      <h5 class="card-title">{{store.SerieFind[index].title}}</h5>
                      <!-- <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p> -->
                    </div>
                    <ul class="list-group list-group-flush">
                      <li class="list-group-item">{{store.SerieFind[index].original_name}}</li>
                      <li class="list-group-item">Lingua: {{store.SerieFind[index].original_language}}</li>
                      <li class="list-group-item">Voto: {{store.SerieFind[index].vote_average}}</li>
                    </ul>
                </div>
            </div>
        </div>

    </div>
</template>





<style lang="scss" scoped>

div {
    display: flex;
    flex-direction: column;
    margin-bottom: 1rem;
    gap: 0.8rem;
    justify-content: space-start;

    .card-container {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        overflow: auto;

        .card {
            height: 46rem;
        }
    }

    h2 {
        color: white;
        font-weight: bold;
        border-top: solid white 0.1rem;

    }


}



</style>