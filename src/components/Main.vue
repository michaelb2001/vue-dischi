<template>
    <div class="container-fluid">

        <Header />

        <div class="row align-items-start justify-content-center text-center">

            <Canzone 
            v-for="(canzone,index) in mioArray" 
            :key="index"
            :info="canzone"
            class="col-12 col-sm-6 g-5 p-3" />
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
        }
    },
    created(){
        this.getCanzoni();
    },
    methods: {
        getCanzoni(){
            axios
                .get(this.apiUrl)
                .then( (risposta) => {
                    // handle success
                    this.mioArray = risposta.data.response;
                    console.log(this.mioArray);
                    console.log(risposta.data.response);
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
}
.row{
    background-color: $bg-body;
}
</style>