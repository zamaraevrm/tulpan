<template>
    <Carousel>
    <Slide :key="slide">
      <img src="../assets/image1.png" class="unselectable" draggable="false">
    </Slide>
    <Slide :key="slide">
      <img src="../assets/image2.jpg" class="unselectable" draggable="false">
    </Slide>
    <Slide :key="slide">
      <img src="../assets/image3.jpg" class="unselectable" draggable="false">
    </Slide>
     <template #addons>
      <Navigation />
    </template>
  </Carousel>
</template>
   
<script>
import { Carousel, Slide, Navigation } from 'vue3-carousel' 
import '../../node_modules/vue3-carousel/dist/carousel.css'
export default {
  name: 'PhotoCarousel',
  data () {
    return {
    }
  },
  components: {
    Carousel,
    Slide,
    // Pagination,
     Navigation,
  },
  methods:{
  }
}
</script>
<style>
.unselectable {
  user-drag: none; 
  user-select: none;
  -moz-user-select: none;
  -webkit-user-drag: none;
  -webkit-user-select: none;
  -ms-user-select: none;
}

.carousel {
  border-radius: 15px;
  width: 70%;
}
.carousel li{
  width: 100%!important;
}
.carousel img{
  width: 100%;
  height: 100%;
  border-radius: 15px;
}

@media (max-width: 800px) {
  .carousel {
    border-radius: 15px;
    /*height: 100px;*/
    width:auto;
  }

  .carousel img {
    border-radius: 15px;
    width: 100%;
  }

  .carousel button {
    border-radius: 15px;
    background-color: rgba(255, 255, 255, 0.6);
  }

  .carousel__pagination-item {
    /*margin-top: -6%;*/
  }
}
</style>