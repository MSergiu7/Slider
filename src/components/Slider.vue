<template>
  <div class="container">
    <carousel-3d
      :space="200"
      :width="640"
      :height="426"
      :perspective="35"
      :display="7"
      :border="1"
      :controls-prev-html="'&#10094;'"
      :controls-next-html="'&#10095;'"
      :controls-visible="true"
      :clickable="false"
    >
      <slide v-for="(slide, i) in slides" :index="i" :key="i">
          <img
          :key=index
          :src="'src/assets/slide' + slide + '.jpg'"
          alt="photo in carousel"
          >
      </slide>
    </carousel-3d>
    <!-- <img src="../assets/slide1.jgp" alt=""> -->
  </div>
</template>

<script>

  import {Carousel3d, Slide} from 'vue-carousel-3d'

  export default {

    data() {
      return {
        index: 1,
        slides: 7
      }
    },
    components: {
      Carousel3d,
      Slide
    }
  }
</script>

<style>

  .container {
    display: flex;
    width: 1200px;
    margin: 0 auto;
    position: relative;
  }

  .prev span, .next span {
    color: rgb(47, 141, 210);
  }

   .carousel-3d-slide {
    border: 0;
    background-color: rgba(0, 0, 0, 0);
  }

  .carousel-3d-slide img {
    opacity: 0.3
  }

  .carousel-3d-slide.current img {
    opacity: 1;
  }

</style>
