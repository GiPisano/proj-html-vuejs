<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppFooter from "./components/AppFooter.vue";

export default {
  data() {
    return {
      links: [
        {
          text: "HOME",
          active: false,
        },
        {
          text: "BLOG",
          active: false,
        },
        {
          text: "EVENTS",
          svg: "./src/assets/svg/dropdown.svg",
          active: false,
        },
        {
          text: "GALLERY",
          active: false,
        },
        {
          text: "ABOUT US",
          active: false,
        },
        {
          text: "CONTACT US",
          active: false,
        },
        {
          text: "SHOP",
          active: false,
        },
      ],
    };
  },

  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },
};
</script>

<template>
  <app-header :links="links"></app-header>
  <app-main></app-main>
  <app-footer></app-footer>
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
