<template>
    <div class="container-fluid">
 
        <div class="row align-items-center">
            <div class="col-3">
                <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/768px-Spotify_logo_without_text.svg.png"
                alt="logo spotify">
            </div>

            <div class="col-9">
                <Cerca />
            </div>


        </div>

    </div>
</template>

<script>
import Cerca from './commons/Cerca.vue'
export default {
    name: "Header",
    components:{
        Cerca
    }
}
</script>

<style lang="scss" scoped>

@import '../assets/vars.scss';
.container-fluid{
    background-color:$bg-header;

    img{
        height: 50px;
        width: auto;
        margin: 10px;
    }
}

</style>