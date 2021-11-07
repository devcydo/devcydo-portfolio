<script>

    import { library } from '@fortawesome/fontawesome-svg-core';
	import { faCode, faAngleDown, faServer, faEllipsisH,
			faLanguage, faEye} from '@fortawesome/free-solid-svg-icons';
	import { FontAwesomeIcon } from 'fontawesome-svelte';

    library.add(faCode);
	library.add(faAngleDown);
	library.add(faServer);
	library.add(faEllipsisH);
	library.add(faLanguage);
	library.add(faEye);

    //Events variables
    let toggleSkills = 'skills_close'

    //Variables received
    export let skillName = ''
    export let skills = []
    export let imgs = []
    export let icon = ''
</script>

<div>
    <div class="skills_content {toggleSkills}">
        <div on:click="{() => toggleSkills = (toggleSkills == 'skills_close') ? 'skills_open':'skills_close'}"
            class="skills_header"
        >
            <FontAwesomeIcon icon={icon} class="skills_icon"/>

            <div>
                <h1 class="skills_title">{skillName}</h1>
                <span class="skills_subtitle"></span>
            </div>
            
            <FontAwesomeIcon  
                icon="angle-down" 
                class="skills_arrow"
            />
        </div>

        <div class="skills_list grid">
            {#each skills as skill, i}
                <div class="skills_data">
                    <div class="skills_title">
                        {#if imgs.length > 0}
                            <img src={imgs[i]} alt="" class="skills_img">
                        {/if}
                        <h3 class="skills_name">{skill}</h3>
                    </div>
                </div>
            {/each}
        </div>
    </div>
</div>