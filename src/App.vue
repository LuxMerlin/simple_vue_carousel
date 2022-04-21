<template>
  <carousel
            @next="next"
            @prev="prev">
    <carousel-slide v-for="(slide, index) in slides" 
                    :key="slide" 
                    :index="index"
                    :visiableSlide="visiableSlide"
                    :direction="direction">
      <img :src="slide"/>
    </carousel-slide>
  </carousel>
  <div>
  </div>
</template>

<script>
import Carousel from './components/Carousel.vue';
import CarouselSlide from './components/CarouselSlide.vue';
export default {
  name: 'App',
  data() {
    return {
      slides: [
        'https://picsum.photos/id/13/600/350',
        'https://picsum.photos/id/423/600/350',
        'https://picsum.photos/id/103/600/350',
        'https://picsum.photos/id/23/600/350',
        'https://picsum.photos/id/12/600/350',
        'https://picsum.photos/id/523/600/350'
      ],
      visiableSlide: 0,
      direction: 'left'
    }
  },
  computed: {
    slideLen(){
      return this.slides.length - 1;
    }
  },
      methods: {
        next(){
          if (this.visiableSlide >= this.slideLen) {
            this.visiableSlide = 0;
          }else{
            this.visiableSlide++;
          }
          this.direction = 'left'
        },
        prev(){
          if (this.visiableSlide <= 0) {
            this.visiableSlide = this.slideLen;
          }else{
            this.visiableSlide--;
          }
          this.direction = 'right'
        }
    },
  components : {
    Carousel,
    CarouselSlide,
  }
}
</script>

<style>
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;

  padding: 0;
  margin: 0;
}

#app{
  display: flex;
  justify-content: center;
}
</style>
