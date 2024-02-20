<script>

export default{
    
    data(){
        return{
            cards:[
                {
                    phat_svg: '/src/assets/svg/speaker.svg',
                    title: 'ORIGINAL IDEAS',
                    description: 'Contrary Popular Belief, Lorem Ipsum Not Simply Ipsum Random Text.'
                },
                {
                    phat_svg: '/src/assets/svg/disc.svg',
                    title: 'MUSIC STUDIO',
                    description: 'Contrary Popular Belief, Lorem Ipsum Not Simply Ipsum Random Text.'
                },
                {
                    phat_svg: '/src/assets/svg/headphones.svg',
                    title: 'ACOUSTIC COVERS',
                    description: 'Contrary Popular Belief, Lorem Ipsum Not Simply Ipsum Random Text.'
                },
            ]
        }
    },


}
</script>

<template>
    <div class="container text-center" id="jazz">
        <div class="row-card">
            <div v-for="card in cards" class="col-card">
                <div class="container-card">
                    <img :src="card.phat_svg" class="svg" alt="">
                    <p>{{ card.title }}</p>
                    <p>{{ card.description }}</p>
                </div>
            </div>
        </div>

        <div class="story-jazz">
            <p class="orange">WHO WE ARE</p>
            <p class="title">SENSE THE JAZZ</p>
            <p>The Story Of Jazz And Blues Society Is The Story Of Determination, Passion, Idealism, Community, And Of Course, Music. Founded In 1985 And Incorporated In 1986, As A Community Based, Not-For-Profit, Charitable Arts Organization Located In Vancouver, British Columbia, The Society, From The Very Beginning, Has Worked Diligently To Establish Vancouver As A Centre For The Creation And Exchange Of Sounds And Ideas Between The Local, National And International Music Communities.</p>
            <p class="button">READ MORE</p>
        </div>
    </div>

  
    <section class="img-video">
        <img src="../assets/img/Video.jpg" alt="">
        <div class="video">
            <i class="fa-regular fa-circle-play orange"></i>
            <p class="title">NEW MUSIC VIDEO</p>
        </div>
    </section>

</template>

<style lang="scss" scoped>
@use '../styles/partials/mixins.scss' as *;
.row-card{
    @include flex;
    gap: 20px;
}

.svg{
    filter: brightness(0) invert(1);
    max-height: 88px;
    padding-bottom: 10px;
}

.container-card{
    @include flex;
    flex-direction: column;
    gap: 15px;
    background-color: rgb(15, 15, 15);
    padding: 10% ;
    max-width: 350px;
    width: 100%;
    height: 300px;
}

.story-jazz{
    @include flex;
    flex-direction: column;
    gap: 10px;
    margin: 40px auto;
    max-width: 650px;
}

.title{
    font-size: 40px;
    font-weight: bold;
}

.button{
    margin-top: 10px;
}

.img-video{
    position: relative;
    img{
        width: 100%;
    }

    .orange{
        font-size: 70px;
    }
}
</style>