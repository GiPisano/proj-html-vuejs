<script>
import SectionRock from "./MainSectionRock.vue";
import SectionJazz from "./MainSectionJazz.vue";

export default {
  data() {
    return {
      infoSongs: [
        {
          svg: "./svg/man.svg",
          number: 163,
          description: "ALL CONCERTS",
        },
        {
          svg: "./svg/rocket.svg",
          number: 145,
          description: "HAPPY CLIENTS",
        },
        {
          svg: "./svg/trophy.svg",
          number: 72,
          description: "MUSIC AWARDS",
        },
        {
          svg: "./svg/music.svg",
          number: 182,
          description: "TOTAL SONGS",
        },
      ],

      bestSongs: [
        {
          img: "./img/hip_hop.jpg",
          title: "HIP HOP WIRED TO DANCE MAKE",
          date: "06 November 2021",
          description:
            "Driving Short Distances Music Is A Music Genre That Includes Traditional Folk Music And The Contemporary Genre That Evolved From The Former",
        },
        {
          img: "./img/music_business.jpg",
          title: "MUSIC BUSINESS WORLDWIDE",
          date: "27 May 2022",
          description:
            "Accelerate Work And Drive Productivity The Beatles Experimentation And Creative Freedom Led Other Bands To Experiment In Various Ways As Well.",
        },
        {
          img: "./img/giveaways_rock.jpg",
          title: "GIVEAWAYS ROCK TO ALL",
          date: "07 May 2022",
          description:
            "Signs Your Car Battery Has To Be Replaced When The Dashboard Lights Start Flashing, This Is A Sign The Battery Is Dying. Several Issues Arise And",
        },
      ],

      imagesGallery: [
        "./img/instagram_img4.jpg",
        "./img/instagram_img5.jpg",
        "./img/instagram_img6.jpg",
        "./img/instagram_img7.jpg",
        "./img/instagram_img8.jpg",
        "./img/instagram_img9.jpg",
        "./img/instagram_img10.jpg",
        "./img/instagram_img1.jpg",
      ],
    };
  },

  components: {
    SectionRock,
    SectionJazz,
  },
};
</script>

<!-- html -->
<template>
  <section-rock />
  <section-jazz />

  <!-- video rock -->
  <section class="img-video">
    <img src="/img/cms_parallax.jpg" alt="" />
    <div class="container">
      <div class="video-rock">
        <p class="orange">INSTRUMENTAL ROCK</p>
        <p class="title">ALBUM OUT NOW</p>
        <p class="button">READ MORE</p>
      </div>
    </div>
  </section>

  <!-- info music -->
  <div class="img-info-music">
    <img src="/img/counter_parallax.jpg" class="img-background" alt="" />
    <div class="container">
      <section class="info-music">
        <div class="row">
          <div class="col" v-for="infoSong in infoSongs">
            <img :src="infoSong.svg" alt="" />
            <p class="title">{{ infoSong.number }}</p>
            <p class="description">{{ infoSong.description }}</p>
          </div>
        </div>
      </section>
    </div>
  </div>

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
            <img :src="bestSong.img" alt="" />
            <p class="title-card">{{ bestSong.title }}</p>
            <p class="orange">
              <span><i class="fa-solid fa-calendar-days"></i></span>
              {{ bestSong.date }}
            </p>
            <p class="description-card">{{ bestSong.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- gallery -->
  <section id="gallery">
    <div class="row">
      <div class="col-gallery" v-for="imageGallery in imagesGallery">
        <img :src="imageGallery" alt="" />
      </div>
    </div>
  </section>
</template>

<!-- style -->
<style lang="scss" scoped>
@use "../styles/partials/mixins.scss" as *;

// video rock
.img-video {
  position: relative;
  img {
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
  .title {
    font-size: 70px;
  }
}

// info music
.img-info-music {
  position: relative;

  .img-background {
    width: 100%;
    height: 350px;
    object-fit: cover;
  }

  .info-music {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    text-align: center;

    .row {
      display: flex;
      justify-content: center;
    }

    .col {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 10px;

      img {
        filter: brightness(0) invert(1);
        height: 60px;
      }

      .title {
        font-size: 40px;
      }

      .description {
        font-weight: bold;
      }
    }
  }
}

// best music
#best-music {
  padding: 100px 0;
  img {
    width: 100%;
  }

  .container-card {
    max-width: 350px;
    gap: 15px;
    display: flex;
    flex-direction: column;

    .orange,
    .description-card {
      font-size: 12px;
    }
  }

  .title {
    font-size: 40px;
    font-weight: bold;
    padding: 20px;
  }

  .title-card {
    font-weight: bold;
  }

  .description-card {
    color: rgb(157, 157, 157);
  }
}

// gallery
#gallery {
  img {
    width: 100%;
  }
  .col-gallery {
    display: flex;
    width: calc(100% / 8);
    padding: 0 0 100px 0;
  }

  .row {
    margin-left: 0;
    margin-right: 0;
  }
}

@media screen and (max-width: 768px) {
  .img-video {
    .container {
      .title {
        font-size: 20px;
      }
      .orange {
        font-size: 12px;
      }
    }
  }
  // info music
  .info-music {
    .col {
      gap: 5px;
      .title {
        font-size: 20px;
      }
    }
  }
}
</style>
