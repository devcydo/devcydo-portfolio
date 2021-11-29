
<script>
    import { Swiper, SwiperSlide } from 'swiper/svelte';
    import { library } from '@fortawesome/fontawesome-svg-core';
	import { faArrowRight, faInfo } from '@fortawesome/free-solid-svg-icons';
	import { FontAwesomeIcon } from 'fontawesome-svelte';
    //Modal
    import { getContext } from 'svelte';
	import { fly } from 'svelte/transition';
	
    import Popup from './Popup.svelte';
	import Dialog from './Dialog.svelte';
	import CloseButton from './CloseButton.svelte';

    const { open } = getContext('simple-modal');
	
	let opening = false;
	let opened = false;
	let closing = false;
	let closed = false;
    const showPopup = () => {
		open(Popup);
	};
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
    library.add(faInfo)

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
                    {#if slide.title == 'AQUATA'}
                        <a on:click={showPopup} href="#" class="button button_flex button_small portfolio_button">
                            INFO
                            <FontAwesomeIcon icon="info" class="button_icon"/>
                        </a>
                        <a  href="https://gitlab.com/larapa/aquata-2.0" target="_blank" class="button button_flex button_small portfolio_button">
                            REPO
                            <FontAwesomeIcon icon="arrow-right" class="button_icon"/>
                        </a>
                    {:else}
                        <a href={slide.link} target="_blank" class="button button_flex button_small portfolio_button">
                            VISIT
                            <FontAwesomeIcon icon="arrow-right" class="button_icon"/>
                        </a>
                    {/if}
                </div>
            </div>
        </SwiperSlide>
    {/each}
</Swiper>