<template>
  <div class="container">
    <carousel-3d
      dir="ltr"
      :space="200"
      :perspective="35"
      :display="7"
      :border="10"
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
  </div>
</template>

<script>

  import {Carousel3d, Slide} from 'vue-carousel-3d'

  export default {

    data() {
      return {
        height: 426,
        width: 640,
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

  html, body {
    overflow-x: hidden;
  }

  .container {
    display: flex;
    max-width: 1200px;
    margin: 0 auto;
    position: relative;
  }

  .prev span, .next span {
    color: rgb(47, 141, 210);
  }

   .carousel-3d-slide {
    border: 0;
    /* border: 50px solid green; */

    background-color: rgba(0, 0, 0, 0);
  }

  .carousel-3d-slide img {
    opacity: 0.3
  }

  .carousel-3d-slide.current img {
    opacity: 1;
  }

  .left-1 {
    transform: translateX(250px) translateZ(-400px) rotateY(-35deg) !important;
  }

  .right-1 {
    transform: translateX(-250px) translateZ(-400px) rotateY(35deg) !important;
  }

  .carousel-3d-container {
    height: 426px !important;
    width: 100% !important;
  }

  .carousel-3d-slider, .carousel-3d-slide {
    height: 426px !important;
    width: 640px !important;
    /* border: 5px solid blue; */

  }

  @media screen and (max-width: 1225px) {
    .carousel-3d-slider, .carousel-3d-slide {
      /* border: 5px solid red; */
      width: 320px !important;
      height: 215px !important;
    }

    .carousel-3d-container {
      height: 215px !important;
      max-width: 70% !important;
      overflow: hidden !important;
    }

    .left-1 {
      transform: translateX(150px) translateZ(-400px) rotateY(-35deg) !important;
    }

    .right-1 {
      transform: translateX(-150px) translateZ(-400px) rotateY(35deg) !important;
    }

    .left-2 {
      transform: translateX(250px) translateZ(-500px) rotateY(-35deg) !important;
    }

    .right-2 {
      transform: translateX(-250px) translateZ(-500px) rotateY(35deg) !important;
    }

    .left-3 {
      transform: translateX(350px) translateZ(-600px) rotateY(-35deg) !important;
    }

    .right-3 {
      transform: translateX(-350px) translateZ(-600px) rotateY(35deg) !important;
    }
  }

  @media screen and (max-width: 992px) {
    .carousel-3d-slider, .carousel-3d-slide {
      /* border: 5px solid red; */
      width: 160px !important;
      height: 110px !important;
    }

    .carousel-3d-container {
      height: 110px !important;
      max-width: 70% !important;
      overflow: hidden !important;
    }
  }

</style>
