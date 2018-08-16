<template>
  <div class="container">
    <i class="fas fa-angle-left" @click="prev"></i>
    <app-slide :index="index"></app-slide>
    <i class="fas fa-angle-right" @click="next"></i>
  </div>
</template>

<script>
  import Slide from './Slide.vue'
  export default {

    data() {
      return {
        index: 1
      }
    },
    components: {
      appSlide: Slide
    },
    methods: {
      next() {
        if (this.index == 6) {
          this.index = 1;
        } else {
          this.index ++;
        }
      },
      prev() {
        if (this.index == 1) {
          this.index = 6;
        } else {
          this.index --;
        }
      }
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

  .fas {
    font-size: 50px;
    color: rgb(47, 141, 210);
    cursor: pointer;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
  }

  .fa-angle-left {
    left: 0;
  }

  .fa-angle-right {
    right: 0;
  }

  .flip-enter-active {
    animation: flip-in 0.5s linear forwards;
  }

  .flip-leave-active {
    animation: flip-out 0.5s linear forwards;
  }

  @keyframes flip-out {
    from {
      opacity: 1;
      transform: rotateY(0deg);
    }
    to {
      opacity: 0.3;
      transform: rotateY(45deg);
    }
  }

  @keyframes flip-in {
    from {
      opacity: 0.3;
      transform: rotateY(-45deg);
    }
    to {
      opacity: 1;
      transform: rotateY(0deg);
    }
  }

</style>
