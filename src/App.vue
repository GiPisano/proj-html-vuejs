<script>
import AppHeader from './components/AppHeader.vue';

export default{
  data(){
    return{
      title: 'proj html vuejs'
    }
  },
  
  components:{
    AppHeader,
  },
}
</script>

<template>
  <app-header></app-header>
  <h1>{{ title }}</h1>
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
