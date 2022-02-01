<template>
  <div class="cerca">
    <label for="genres">Genres : </label>

    <select name="genres" id="genres">
    <option value=""></option>
    </select>
  </div>
</template>

<script>
export default {
    name:"Cerca",
    props:{
        opzioni : Object
    }
}
</script>

<style lang="scss" scoped>
    .cerca{
        margin-left: 90px;
    }
</style>