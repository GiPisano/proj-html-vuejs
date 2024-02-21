<script>
import SectionRock from './MainSectionRock.vue';
import SectionJazz from './MainSectionJazz.vue';

export default{
    data(){
        return{
            infoSongs: [
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
            ],

            bestSongs: [
                {
                    img: '/src/assets/img/hip_hop.jpg',
                    title: 'HIP HOP WIRED TO DANCE MAKE',
                    date: '06 November 2021',
                    description: 'Driving Short Distances Music Is A Music Genre That Includes Traditional Folk Music And The Contemporary Genre That Evolved From The Former',
                },
                {
                    img: '/src/assets/img/music_business.jpg',
                    title: 'MUSIC BUSINESS WORLDWIDE',
                    date: '27 May 2022',
                    description: 'Accelerate Work And Drive Productivity The Beatles Experimentation And Creative Freedom Led Other Bands To Experiment In Various Ways As Well.',
                },
                {
                    img: '/src/assets/img/giveaways_rock.jpg',
                    title: 'GIVEAWAYS ROCK TO ALL',
                    date: '07 May 2022',
                    description: 'Signs Your Car Battery Has To Be Replaced When The Dashboard Lights Start Flashing, This Is A Sign The Battery Is Dying. Several Issues Arise And',
                },
            ]
        }
    },

    components:{
        SectionRock, SectionJazz,
    },
}
</script>


<!-- html -->
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
                <div class="col" v-for="infoSong in infoSongs">
                    <img :src="infoSong.svg" alt="">
                    <p>{{ infoSong.number }}</p>
                    <p>{{ infoSong.description }}</p>
                </div>
            </div>
        </div>
    </section>

    <!-- best music -->
    <section id="best-music">
        <div class="container">
            <div class="text-center">
                <p class="orange">MUSIC BLOG</p>
                <p class="title">BEST MUSIC BLOG</p>
            </div>
            <div class="row-card">
                <div class="col-card" v-for="bestSong in bestSongs">
                    <div class="container-card">
                        <img :src="bestSong.img" alt="">
                        <p>{{ bestSong.title }}</p>
                        <p class="orange">
                            <span><i class="fa-solid fa-calendar-days"></i></span>
                            {{ bestSong.date }}
                        </p>
                        <p>{{ bestSong.description }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
    


</template>


<!-- style -->
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

    // best music
    #best-music{
        img{
            width: 100%;
        }

        .container-card{
            max-width: 350px;
            .orange{
                font-size: 14px;
            }
        }

        .title{
            font-size: 40px;
            font-weight: bold;
        }

        
    }
</style>