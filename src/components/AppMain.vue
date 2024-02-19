<script>
export default{
}
</script>

<template>
    <section id="rock-video">
        <img src="../assets/img/imageVideo.png" alt="">
        <div class="video">
            <p class="music-genre">INSTRUMENTAL ROCK</p>
            <p class="info">MUSIC IN THIS VIDEO</p>
            <p class="button">READ MORE</p>
        </div>
    </section>
    
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

#rock-video{
    position: relative;
}

img{
width: 100%;

}

.video{
    text-align: center;
    position: absolute;
    top: 50%;
    left: 50%; 
    transform: translate(-50%, -50%); 
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 50px;
}

.music-genre{
    color: $orange-color;
}

.info{
    font-size: 60px;
    font-weight: bold;
}

.button{
    border: 1px solid $orange-color;
    padding: 10px 40px;
    width: auto;
}

</style>