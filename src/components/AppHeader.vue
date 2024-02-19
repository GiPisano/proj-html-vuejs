<script>
export default{
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
            <p v-for="link in links" class="link">{{ link.text }}</p>
            <img class="search" src="../assets/svg/search.svg" alt="">
        </div>
    </header>
    
</template>

<style lang="scss" scoped>
.logo{
    color: white;
    width: 120px;
}
.search{
    filter: brightness(0) invert(1);
}

header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
}

.links{
    display: flex;
    gap: 10px;
}

.link:hover{
    color: #F2870C;
}


</style>