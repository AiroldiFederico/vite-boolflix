<script>
    import {store} from '../store'
    import CardFilmComp from "./CardFilmComp.vue"
    export default{
        
        name: "MainComp",
        
        components: {
            CardFilmComp,
        },

        data(){
            return{
               

                store,

            }
        },

    }
    
</script>



<!-- MAIN -->
<template>
    <div id="NameComp" class="bg-dark">
        <CardFilmComp/>
    </div>
</template>





<style lang="scss" scoped>

    div {

        //height:calc(100vh - 5.3rem);
        min-height:calc(100vh - 5.3rem) ;
        padding: 2rem;


        .card {
            height: 5rem;
        }


    }


</style>