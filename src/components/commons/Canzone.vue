<template>
  <div class="container-fluid m-5 p-3">
    <div class="row flex-column align-items-start justify-content-start flex-wrap text-wrap p-3">
      <img :src='info.poster' alt="info.title">

      <h2>{{info.title}}</h2>

      <p>{{info.author}}</p>

      <p>{{info.year}}</p>

    </div>
  </div>
</template>

<script>
export default {
    name:"Canzone",
    props:{
        info : Object
    }
}
</script>

<style lang="scss" scoped>
@import "../../assets/vars.scss";

.container-fluid{
    background-color: $bg-header;
    min-height: 450px;
    width: 200px;
    border-radius: 2px;
    .row{


        img{
        width: 100%;
        border-radius: 2px;
        }

        h2{
            color: $h-color;
        }

        p{
            color: $p-color;
        }
    }

}


</style>