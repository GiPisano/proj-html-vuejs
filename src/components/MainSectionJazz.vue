<script>
import cardJazz from "./CardJazz.vue";

export default {
  data() {
    return {
      cardsInfo: [
        {
          phat_svg: "./src/assets/svg/speaker.svg",
          title: "ORIGINAL IDEAS",
          description:
            "Contrary Popular Belief, Lorem Ipsum Not Simply Ipsum Random Text.",
        },
        {
          phat_svg: "./src/assets/svg/disc.svg",
          title: "MUSIC STUDIO",
          description:
            "Contrary Popular Belief, Lorem Ipsum Not Simply Ipsum Random Text.",
        },
        {
          phat_svg: "./src/assets/svg/headphones.svg",
          title: "ACOUSTIC COVERS",
          description:
            "Contrary Popular Belief, Lorem Ipsum Not Simply Ipsum Random Text.",
        },
      ],

      cardsJazz: [
        {
          phat_img: "./src/assets/img/gallery1.jpg",
          title: "A ROLL AND BANG THE FLOOR",
        },
        {
          phat_img: "./src/assets/img/gallery2.jpg",
          title: "YOUR MELODY TO OUR MUSIC",
        },
        {
          phat_img: "./src/assets/img/gallery3.jpg",
          title: "TOUCHING HEAVEN ON FREQUENCY",
        },
        {
          phat_img: "./src/assets/img/gallery4.jpg",
          title: "MUSIC MAKES STRONGE BEATS",
        },
        {
          phat_img: "./src/assets/img/gallery5.jpg",
          title: "SOUND IS THE SPARK OF TIME",
        },
        {
          phat_img: "./src/assets/img/gallery6.jpg",
          title: "MAKE YOUR NIGHT GROOVY",
        },
      ],
    };
  },

  components: { cardJazz },
};
</script>

<template>
  <!-- Jazz -->
  <div class="container text-center" id="jazz">
    <div class="row-card">
      <div v-for="cardInfo in cardsInfo" class="col-card">
        <div class="container-card">
          <div class="circle-svg">
            <img :src="cardInfo.phat_svg" class="svg" alt="" />
          </div>
          <p>{{ cardInfo.title }}</p>
          <p>{{ cardInfo.description }}</p>
        </div>
      </div>
    </div>

    <!-- story jazz -->
    <div class="story-jazz">
      <p class="orange">WHO WE ARE</p>
      <p class="title">SENSE THE JAZZ</p>
      <p class="description">
        The Story Of Jazz And Blues Society Is The Story Of Determination,
        Passion, Idealism, Community, And Of Course, Music. Founded In 1985 And
        Incorporated In 1986, As A Community Based, Not-For-Profit, Charitable
        Arts Organization Located In Vancouver, British Columbia, The Society,
        From The Very Beginning, Has Worked Diligently To Establish Vancouver As
        A Centre For The Creation And Exchange Of Sounds And Ideas Between The
        Local, National And International Music Communities.
      </p>
      <p class="button">READ MORE</p>
    </div>
  </div>

  <!-- video -->
  <section class="img-video">
    <img src="../assets/img/Video.jpg" alt="" />
    <div class="video">
      <i class="fa-regular fa-circle-play orange"></i>
      <p class="title">NEW MUSIC VIDEO</p>
    </div>
  </section>

  <!-- cards jazz -->
  <div class="container text-center" id="card-jazz">
    <p class="orange">WHO WE ARE</p>
    <p class="title">SENSE THE JAZZ</p>
    <div class="row-card">
      <card-jazz
        v-for="cardJazz in cardsJazz"
        :cardsJazz="cardJazz"
      ></card-jazz>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/mixins.scss" as *;

#jazz {
  .circle-svg {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;

    .svg {
      filter: brightness(0) invert(1);
      height: 88px;
    }
  }

  .col-card {
    .container-card {
      background-color: rgb(15, 15, 15);
      max-width: 350px;
      width: 100%;
      height: 350px;
      padding: 10%;
      gap: 15px;
      @include flex;
      flex-direction: column;
    }
  }
}

.col-card:hover {
  .circle-svg {
    box-shadow: 0 0 0 5px rgba(255, 165, 0, 1); // Arancione
  }
}

.story-jazz {
  @include flex;
  flex-direction: column;
  gap: 10px;
  margin: 40px auto;
  max-width: 650px;

  .description {
    color: rgb(157, 157, 157);
    font-size: 12px;
  }

  .button {
    margin-top: 10px;
  }
}

.title {
  font-size: 40px;
  font-weight: bold;
}

.img-video {
  position: relative;
  img {
    width: 100%;
  }

  .orange {
    font-size: 70px;
  }
}

#card-jazz {
  padding: 100px 0;

  .title {
    padding: 20px;
  }
}
</style>
