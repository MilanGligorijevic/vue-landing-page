<template>
    <Carousel ref="myCarousel" class="carousel" >
      <Slide v-for="slide in 3" :key="slide" >
        <div class="carousel__item">
          <img src="../assets/slider-image-small.png" class="slider-image-small"/>
          <img src="../assets/slider-image-medium.png" class="slider-image-medium"/>
          <img src="../assets/slider-image-large.png" class="slider-image-large"/>
          <div class="slider-bottom-part"> 
            <div v-on:click="prevSlide" class="arrow arrow-prev"></div>
            <div class="slider-title">LOREM IPSUM DOLOR SIT</div>
            <div v-on:click="nextSlide" class="arrow arrow-next"></div>
          </div>
        </div>
        
      </Slide>
      <template #addons>  
          <!-- <Navigation class="navigation"/> -->
          <Pagination class="pagination"/>
        </template>
    </Carousel>
    
  </template>
  
  <script>
  import { defineComponent } from 'vue'
  import { Carousel, Navigation, Pagination, Slide } from 'vue3-carousel'
  
  import 'vue3-carousel/dist/carousel.css'
  
  export default defineComponent({
    name: 'Basic',
    components: {
      Carousel,
      Slide,
      Pagination,
      Navigation,
    },
    methods: {
      nextSlide(){
        const myCarousel = this.$refs.myCarousel;
        myCarousel.next();
      },
      prevSlide(){
        const myCarousel = this.$refs.myCarousel;
        myCarousel.prev();
      }
    }
  })
  </script>
  
  <style>
  .carousel__item {
    width: 100%;
    min-height: 11.8rem;
    /* background-image: url('../assets/slider-image-small.png');
    background-repeat: no-repeat;
    background-size: cover; */
    font-size: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  
  /* navigatiion preko mojih strelica, uz metode iz Carousel komponente*/
  .arrow{
    width: .9rem;
    height: .9rem;
    border-color: #9d9d9c;
  }

  .arrow-prev{
    border-bottom: .3rem solid #9d9d9cb7;
    border-left: .3rem solid #9d9d9cb7;
    transform: rotate(45deg);
  } 
   
  .arrow-next{
    border-bottom: .3rem solid #9d9d9cb7;
    border-left: .3rem solid #9d9d9cb7;
    transform: rotate(-135deg);
  }

  .pagination{
    display: none;
  }
  
  .carousel__prev,
  .carousel__next {
    box-sizing: content-box;
  }
  .carousel__track{
    margin: 0;
  }

  .slider-image-small{
    width: 100%;
    height: 100%;
    border-bottom: .1rem solid #D5D5D5;
    object-fit: cover;
  }
  .slider-image-medium{
    display: none;
    width: 100%;
    height: 100%;
    border-bottom: .1rem solid #D5D5D5;
    object-fit: cover;
  }
  .slider-image-large{
    display: none;
    width: 100%;
    height: 100%;
    border-bottom: .1rem solid #D5D5D5;
    object-fit: cover;
  }

  .slider-bottom-part{
    font-size: 1.8rem;
    width: 100%;
    height: 6rem;
    border-bottom: .1rem solid #D5D5D5;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  @media screen and (min-width: 480px){
      .slider-image-medium{
        display: block;
      } 
      .slider-image-small{
        display: none;
      }
      .slider-title{
        display: none;
      }
      .slider-bottom-part{
        display: none;
      }
      .pagination{
        display: flex;
        transform: translateY(-215%); 
      }
      .carousel__pagination-button::after{
        height: .9rem;
        width: .9rem;
        border-radius: 50%;
        background-color: #BABABA;
      }
      .carousel__pagination-button:hover::after,
      .carousel__pagination-button--active::after {
        background-color: #BCD546;
      }
    }

    @media screen and (min-width: 768px){
      .slider-image-medium{
        display: none;
      }
      .slider-image-large{
        display: block;
      }
      .pagination{
        display: flex;
        transform: translateY(-230%); 
      }
    }
  </style>