<template>
  <div id="app">
    <div style="width: 500px;">
      <carrousel>
        <carrouselSlide>
          <!-- Slider 1 -->
          <img :src="imagenes[0]" alt="imagen 1" width="100%">
        </carrouselSlide>
        <carrouselSlide>
          <!-- Slider 2 -->
          <img :src="imagenes[1]" alt="imagen 2" width="100%">
        </carrouselSlide>
      </carrousel>
    </div>
  </div>
</template>

<script>
import img1 from './assets/img1.jpg';
import img2 from './assets/img2.jpg';
import carrousel from './components/carrousel.vue';
import carrouselSlide from './components/carrousel-slide.vue';

export default {
  name: 'app',
  components: {
    carrousel,
    carrouselSlide
  },
  data: () => {
    return {
      imagenes: [img1, img2]
    }
  },
  mounted() {
    // console.log(this)
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  // background: #999;
}
</style>
