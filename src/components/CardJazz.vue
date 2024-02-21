<script>
export default{
    props:{
        cardsJazz: Object,
    },
}
</script>

<template>
    <div class="col-card-jazz">
        <div class="container-card">
            <img :src="cardsJazz.phat_img" alt="">
            <p>{{ cardsJazz.title }}</p>
            <div class="stream">
                <span>stream on:</span>
                    <i class="fa-brands fa-spotify"></i>
                    <i class="fa-brands fa-youtube"></i>
                    <i class="fa-solid fa-music"></i>
                    <i class="fa-solid fa-cloud"></i>
                    <i class="fa-solid fa-compass"></i>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixins.scss' as *;
@use '../styles/partials/variables.scss' as *;
.col-card-jazz{
    
    img{
        width: 100%;
    }

    .container-card{
        max-width: 350px
    }

    .stream{
        @include flex;
        gap: 10px;
        font-size: 12px;
        color: rgb(157, 157, 157);
    }

    .stream i:hover{
        color: $orange-color;
        cursor: pointer;
    }
}
</style>