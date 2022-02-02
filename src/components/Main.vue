<template>
    <div class="container-fluid">

        <Header @cambio2="assegna" :oggetto="mioArray"/>

        <div class="row align-items-start justify-content-center text-center ">

            <Canzone 
            v-for="(canzone,index) in arrayFiltrato" 
            :key="index"
            :info="canzone"
            class="col-12 col-sm-6 p-3" />
        </div>
    </div>
</template>

<script>
import Canzone from './commons/Canzone.vue';
import Header from './Header.vue'
import axios from 'axios';
export default {
    name: "Main",
    components: {
        Canzone,
        Header
    },
    data(){
        return{
            apiUrl : "https://flynn.boolean.careers/exercises/api/array/music",
            mioArray : [],
            variabile : ""
        }
    },
    created(){
        this.getCanzoni();
    },
    computed:{
        arrayFiltrato(){
            console.log(this.mioArray);
            if(this.variabile == "all"){
                return this.mioArray
            } else{
                return this.mioArray.filter((element) => {
                    return element.genre.toLowerCase().includes(this.variabile.toLowerCase());
                });
            }

        }
    },
    methods: {
        assegna( valore) 
        {
            this.variabile = valore;
            console.log(valore);
            console.log(this.variabile);
        },
        getCanzoni(){
            axios
                .get(this.apiUrl)
                .then( (risposta) => {
                    // handle success
                    this.mioArray = risposta.data.response;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        }
    }
}
</script>

<style lang="scss" scoped>

@import '../assets/vars.scss';
.container-fluid{
    padding: 0%!important;
    overflow-x: hidden ;
}
.row{
    background-color: $bg-body;
    --bs-gutter-x:0px!important;
    margin: 0%!important;
    min-height: 100vh;
}
</style>