<script>
    import { library } from '@fortawesome/fontawesome-svg-core';
	import { faHome, faEnvelope, faPhone } from '@fortawesome/free-solid-svg-icons';
	import { faGithubSquare, faLinkedin } from '@fortawesome/free-brands-svg-icons';
	import { FontAwesomeIcon } from 'fontawesome-svelte';

    library.add(faHome)
    library.add(faEnvelope)
    library.add(faPhone)
    library.add(faGithubSquare)
    library.add(faLinkedin)

    export let title = ''
    export let description = ''
    export let icon = ''
</script>

{#if icon == 'github-square' || icon == 'linkedin'}
    <a 
        href={description} target="_blank"
        class="contact_card contact_card_link contact_link"
    >
        <FontAwesomeIcon icon={['fab',icon]} class="contact_icon"/>
        <h3 class="contact_title">{title}</h3>
        <span class="contact_description">{description}</span>
    </a>
{:else}
    <div class="contact_card">
        <FontAwesomeIcon icon={icon} class="contact_icon"/>
        <h3 class="contact_title">{title}</h3>
        <span class="contact_description">{description}</span>
    </div>
{/if}