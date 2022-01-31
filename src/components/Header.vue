<template>
    <div class="container-fluid">
        <div class="row ">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/768px-Spotify_logo_without_text.svg.png"
            alt="logo spotify">
        </div>

    </div>
</template>

<script>
export default {
    name: "Header"
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