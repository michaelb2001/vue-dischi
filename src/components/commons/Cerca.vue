<template>
  <div class="cerca">
    <label for="genres">Genres : </label>

    <select name="genres" id="genres"  @change="$emit('cambio',selezionato)" v-model="selezionato">
        <option v-for="(element,index) in arrayGenres" :key="index" :value="element">
            {{element}}
        </option>
    </select>
  </div>
</template>

<script>
export default {
    name:"Cerca",
    props:{
        opzioni : Array
    },
    data(){
        return {
            arrayGenres : [],
            arrayNames : [],
            selezionato : ""
        }
    },
    watch:{
        opzioni : function(){
                this.riempiArrayGenres()
        }
    },

    mounted(){
        
    },
    methods: {
        riempiArrayGenres(){
            this.opzioni.forEach(element => {
                if(!this.arrayGenres.includes(element.genre)){
                    this.arrayGenres.push(element.genre);
                }
            });
        }
    }
}
</script>

<style lang="scss" scoped>

@import '../../assets/vars.scss';
    .cerca{        
        label{
            color: $h-color;
            margin:0px 20px;
        }
    }
</style>