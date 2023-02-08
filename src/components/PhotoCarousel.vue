
<template>
    <Carousel>
    <Slide :key="slide">
      <img width="500" src="../assets/image1.png" class="unselectable" draggable="false">
    </Slide>
    <Slide :key="slide">
      <img width="500" src="../assets/image2.jpg" class="unselectable" draggable="false">
    </Slide>
    <Slide :key="slide">
      <img width="500" src="../assets/image3.jpg" class="unselectable" draggable="false">
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
img {
  border-radius:15px;
}
.unselectable {
  user-drag: none; 
  user-select: none;
  -moz-user-select: none;
  -webkit-user-drag: none;
  -webkit-user-select: none;
  -ms-user-select: none;
}
.carousel {
  width:610px;
}
.carousel__pagination-item {
  margin-top: -6%;
}
</style>