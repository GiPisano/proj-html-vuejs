<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default{
  data(){
    return{
      links:[
        {
          text: 'HOME',
          active: false
        },
        {
          text: 'BLOG',
          active: false
        },
        {
          text: 'HEVENTS',
          active: false
        },
        {
          text: 'GALLERY',
          active: false
        },
        {
          text: 'ABOUT US',
          active: false
        },
        {
          text: 'CONTACT US',
          active: false
        },
        {
          text: 'SHOP',
          active: false
        },
      ],
    }
  },
  
  components:{
    AppHeader,
    AppMain,
  },
}
</script>

<template>
  <app-header :links="links"></app-header>
  <app-main></app-main>
</template>

<style lang="scss">
@use './styles/general.scss';

</style>
