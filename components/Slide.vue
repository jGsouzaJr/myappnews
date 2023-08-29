<template>
  <div class="slide">
    <img :src="image.url" :alt="image.alt" />
  </div>
</template>

<script>
export default {
  props: {
    image: {
      'url':'https://cdn.pixabay.com/photo/2015/12/12/15/24/amsterdam-1089646_1280.jpg',
      'alt': 'Texto alternativo'
    }
}
};
</script>

<style scoped>
.slide {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
}

.slide img {
  max-width: 100%;
  max-height: 100%;
}
</style>
