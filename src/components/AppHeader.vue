<script>
export default{

    data(){
        return{
            events:[
                {
                    text: 'CHORAL MUSIC'
                }, 
                {
                    text: 'CONCERT BAND'
                }, 
                {
                    text: 'OPERA CONCERTS'
                }, 
                {
                    text: 'SYMPHONY ORCHESTRA'
                }, 
                {
                    text: 'FAMILY CONCERTS'
                }, 
            ]
        }
    },


   props:{
    links: Array,
   },
}
</script>

<template>
    <header>
        <div>
            <img src="../assets/img/logo.png" alt="logo" class="logo">
        </div>
        <div class="links">
            <p v-for="link in links" class="link">
                <a href="#">{{ link.text }}</a>
                <span v-show="link.svg" class="svg"> 
                    <img :src="link.svg" alt="">
                </span>
                <span class="dropdown-content" v-if="link.text === 'EVENTS'">
                    <div v-for="event in events">
                        <p class="element">{{ event.text }}</p>
                        <p class="hr"></p>
                    </div>
                    
                </span>
            </p>
            <img class="search" src="../assets/svg/search.svg" alt="">
        </div>
    </header>
    
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 10px;
}

.logo{
    color: white;
    width: 120px;
}

.links{
    display: flex;
    gap: 20px;
    font-size: 15px;
    font-weight: bold;
}

.search{
    filter: brightness(0) invert(1);
}

// dropdown

.link {
  position: relative;
}

.dropdown-content {
  position: absolute;
  top: 100%;
  left: 0;
  display: none;
  background-color: #fff;
  box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.2);
  z-index: 1;
  background-color: rgb(24, 24, 24);
  min-width: 300px;
}

.element{
    padding: 20px;
}

.element:hover{
    cursor: pointer;
    color: $orange-color;
}

.link:hover .dropdown-content {
    display: flex;
    flex-direction: column;
}

.svg{
    filter: brightness(0) invert(1);
}


</style>