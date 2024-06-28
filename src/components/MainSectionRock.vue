<script>
export default {};
</script>

<template>
  <section id="rock">
    <img src="/img/imageVideo.png" alt="" />
    <div class="video">
      <p class="orange">INSTRUMENTAL ROCK</p>
      <p class="info">MUSIC IN THIS VIDEO</p>
      <p class="button">READ MORE</p>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss" as *;

#rock {
  position: relative;
}

img {
  width: 100%;
}

.video {
  text-align: center;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 32px;
  width: 100%;
}

.orange {
  font-weight: bold;
}

.info {
  font-size: 60px;
  font-weight: bold;
}

@media screen and (max-width: 768px) {
  .info {
    font-size: 30px;
  }
}
</style>
