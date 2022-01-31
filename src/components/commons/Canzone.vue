<template>
  <div class="container-fluid m-5">
      <div class="row flex-column align-items-center justify-content-start flex-wrap text-wrap"></div>
      <img src='info.poster' alt="info.title">

      <h2>{{info.title}}</h2>


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

<style>
    @import '../../assets/vars.scss';
</style>