<script setup>


const { data } = await useAsyncData("marketMix", () =>
  $fetch(
    `https://api.dev.inoutdelivery.com.co/v1/banners?business=ppc.inoutdelivery.com`
  )
);

const urlImg = data._rawValue[0].banners[0].banner.image.lg;
</script>
<template>
  <div class="carousel-container">
    <ol class="carousel-list">
      <li class="carousel-slide"><img :src="urlImg" alt="" /></li>
      <li class="carousel-slide"><img :src="urlImg" alt="" /></li>
      <li class="carousel-slide"><img :src="urlImg" alt="" /></li>
    </ol>
  </div>
</template>

<style scoped>
.carousel-container {
  max-width: 100%;
  max-height: 100vh;
  overflow: hidden;
}
.carousel-list {
  display: flex;
  animation: carousel-animation 10s infinite linear;
}
.carousel-slide {
  width: 100%;
  margin-right: 5px;

  display: inline-block;
}
.carousel-slide img {
  /* width: 100%; */
  margin: 0 5px;
  height: 50vh;
}

@keyframes carousel-animation {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-1500px);
  }
}
</style>