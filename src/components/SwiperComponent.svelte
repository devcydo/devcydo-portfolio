<script>
    import { Swiper, SwiperSlide } from 'swiper/svelte';
    import { library } from '@fortawesome/fontawesome-svg-core';
	import { faArrowRight } from '@fortawesome/free-solid-svg-icons';
	import { FontAwesomeIcon } from 'fontawesome-svelte';

    //Alerts
	import {notifications} from '../services/notifications.js'
	import Toast from './Toast.svelte'
    
    //Swiper
    import 'swiper/css'
    import "swiper/css/pagination"
    import "swiper/css/navigation"
    
    // import Swiper core and required modules
    import SwiperCore, {
    Navigation
    } from 'swiper';

    // install Swiper modules
    SwiperCore.use([Navigation]);


    library.add(faArrowRight)

    export let slides = []
</script>

<Swiper
    navigation="{true}"
    loop="{true}" 
    autoplay="{true}"
    pagination='{{
        "clickable": true
    }}' 
>

    {#each slides as slide }
        <SwiperSlide>
            <div class="portfolio_content grid swiper-slide">
                    <img src={slide.route} alt="" class="portfolio_img">

                    <div class="portfolio_data">
                        <h3 class="portfolio_title">{slide.title}</h3>
                        <p class="portfolio_description">{slide.description}</p>
                        <a href={slide.link} target="_blank" class="button button_flex button_small portfolio_button">
                            Visit
                            <FontAwesomeIcon icon="arrow-right" class="button_icon"/>
                        </a>
                    </div>
                </div>
            </SwiperSlide>
    {/each}
</Swiper>