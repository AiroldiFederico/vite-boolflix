<script>
    import {store} from '../store'
    export default{

        name: "NavBarComp",
        
        components: {
            
        },

        data(){
            return{
               
                store,

            }
        },
        methods: {


        },
    }
    
</script>



<!-- NAVBAR -->
<template>
    <div id="NameComp" class="d-flex justify-content-between bg-dark bg-gradient py-3 px-3">
        <!-- LOGO -->
        <img src="../../public/img/Logo-Netflix.png" alt="Logo Netflix" class="">

        <!-- SEARCH BAR -->
        <form class="d-flex" role="search">
            <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search" v-model="store.SearchBar">
            <button class="btn btn-outline-danger" type="submit" @click.prevent="$emit('nomeEmit')">Search</button>
        </form>

    </div>
</template>





<style lang="scss" scoped>

    div {

        max-height: 5.3rem;

        padding: 0.5rem 1rem !important;
        img {
            width: 12rem;
            height: auto;

        }

        form {
            padding: 1rem 0rem;
        }
    }


</style>