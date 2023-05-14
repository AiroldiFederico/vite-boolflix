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

        methods: {
            getVoteMovie(){
                return Math.ceil(this.store.MovieFind[index].vote_average / 2);
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
                    <img :src="store.MovieFind[index].poster_path ? `https://image.tmdb.org/t/p/w342${store.MovieFind[index].poster_path}` : '../img/noimage.jpg'" class="card-img-top" alt="...">
                    <div class="card-body">
                        <h5 class="card-title">{{store.MovieFind[index].title}}</h5>
                        <!-- <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p> -->
                    </div>
                    <ul class="list-group list-group-flush">
                        <li class="list-group-item">{{store.MovieFind[index].original_title}}</li>
                        <li class="list-group-item">Lingua: {{store.MovieFind[index].original_language}}</li>
                        <li class="list-group-item">Voto:
                            <i v-for="n in 5" class="fa-star" :class=" (n <= Math.ceil(this.store.MovieFind[index].vote_average / 2)) ? 'fa-solid' : 'fa-regular'"></i>
                        </li>
                    </ul>
                </div>
            </div>
        </div>


        <h2>SERIES TV</h2>
        <div class="card-container">
            <div  v-for="(object, index) in store.SerieFind" key="index">
                <div class="card" style="width: 18rem;">
                    <img :src="store.SerieFind[index].poster_path ? `https://image.tmdb.org/t/p/w342${store.SerieFind[index].poster_path}` : '../img/noimage.jpg'" class="card-img-top" alt="...">
                    <div class="card-body">
                      <h5 class="card-title">{{store.SerieFind[index].title}}</h5>
                      <!-- <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p> -->
                    </div>
                    <ul class="list-group list-group-flush">
                      <li class="list-group-item">{{store.SerieFind[index].original_name}}</li>
                      <li class="list-group-item">Lingua: {{store.SerieFind[index].original_language}}</li>
                      <li class="list-group-item">Voto:
                        <i v-for="n in 5" class="fa-star" :class=" (n <= Math.ceil(this.store.SerieFind[index].vote_average / 2)) ? 'fa-solid' : 'fa-regular'"></i>
                      </li>
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

    i {
        color: black;
    }


}



</style>