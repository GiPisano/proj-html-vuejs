<script>
import SectionRock from './MainSectionRock.vue';
import SectionJazz from './MainSectionJazz.vue';

export default{
    data(){
        return{
            infoMusic: [
                {
                    svg: '/src/assets/svg/man.svg',
                    number: 163,
                    description: 'CONCERTS'
                },
                {
                    svg: '/src/assets/svg/rocket.svg',
                    number: 163,
                    description: 'CONCERTS'
                },
                {
                    svg: '/src/assets/svg/trophy.svg',
                    number: 163,
                    description: 'CONCERTS'
                },
                {
                    svg: '/src/assets/svg/music.svg',
                    number: 163,
                    description: 'CONCERTS'
                },
            ]
        }
    },

    components:{
        SectionRock, SectionJazz,
    },
}
</script>

<template>
    <section-rock />
    <section-jazz />

    <!-- video rock -->
    <section class="img-video">
        <img src="/src/assets/img/cms_parallax.jpg" alt="">
        <div class="container">
            <div class="video-rock">
                <p class="orange">INSTRUMENTAL ROCK</p>
                <p class="title">ALBUM OUT NOW</p>
                <p class="button">READ MORE</p>
            </div>
        </div>
    </section>

    <section class="info-music">
        <div class="container">
            <div class="row">
                <div class="col" v-for="info in infoMusic">
                    <img :src="info.svg" alt="">
                    <p>{{ info.number }}</p>
                    <p>{{ info.description }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixins.scss' as *;
    .img-video{
    position: relative;
        img{
            width: 100%;
        }
   
        .video-rock {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: start;
            padding-left: 100px;
            gap: 30px;
        }
        .title{
            font-size: 70px;
        }
    }

    // info music

    .info-music{
        background-image: url('/src/assets/img/counter_parallax.jpg');
        height: 400px;
        text-align: center;
        background-repeat: no-repeat;
        background-position: top;
        @include flex;

        .col{
            @include flex;
            flex-direction: column;
            gap: 10px;
            img{
                filter: brightness(0) invert(1);
                height: 80px;
            }
        }
    }
</style>