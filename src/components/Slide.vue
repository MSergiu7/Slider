<template>
  <transition name="flip" mode="out-in">
    <img
    class="slide-image"
    :key=this.index
    :src="'src/assets/slide' + this.index + '.jpg'"
    alt="photo in slider"
    >
  </transition>
</template>

<script>

  export default {
    props: ['index']
  }

</script>

<style>
  .slide-image {
    margin: 0 auto;
    display: block;
  }
</style>
