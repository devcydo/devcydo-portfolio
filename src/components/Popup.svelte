<script>
    import { Swiper, SwiperSlide } from 'swiper/svelte';
    //Swiper
    import 'swiper/css'
    import "swiper/css/pagination"
    import "swiper/css/navigation"

    // import Swiper core and required modules
    import SwiperCore, {
        Zoom,
        Navigation,
        Pagination
    } from 'swiper';

    // install Swiper modules
    SwiperCore.use([Zoom, Navigation, Pagination]);
    let slides = ['./img/aquata/tepetate_1.png','./img/aquata/tepetate_2.png','./img/aquata/tepetate_3.png','./img/aquata/tepetate_4.png']

  </script>
  
  <Swiper
        zoom="{true}"
        navigation="{true}"
        loop="{true}" 
        autoplay="{true}"
        pagination='{{
            "clickable": true
        }}' 
  >
  
      {#each slides as slide }
          <SwiperSlide>
              <div class="swiper-zoom-container">
                  <img src={slide} alt="" >
              </div>
          </SwiperSlide>
      {/each}
  </Swiper>