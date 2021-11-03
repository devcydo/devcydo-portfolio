<script>
    import { library } from '@fortawesome/fontawesome-svg-core';
	import { faCalendar } from '@fortawesome/free-solid-svg-icons';
	import { FontAwesomeIcon } from 'fontawesome-svelte';

    library.add(faCalendar)

    export let tabTarget = ''
    export let type = ''
    export let info = [{}]
</script>

<div class="experience_content {tabTarget == type ? 'experience_active' : ''}" data-content id=type>
    <!-- Experience1 -->
    {#each info as inf, i}
        {#if i%2 == 0}
            <div class="experience_data">
                <div>
                    <h3 class="experience_title">{inf.name}</h3>
                    <span class="experience_subtitle">{inf.school}</span>
                    {#if inf.desc != ''}
                        <span class="experience_subtitle">{inf.desc}</span>
                    {/if}
                    <div class="experience_calendar">
                        <FontAwesomeIcon icon="calendar"/>
                        {inf.date}
                    </div>
                </div>

                <div>
                    <span class="experience_rounder"></span>
                    <span class="experience_line"></span>
                </div>
            </div>
        {:else}
            <div class="experience_data">
                <div></div>
                <div>
                    <span class="experience_rounder"></span>
                    <span class="experience_line"></span>
                </div>
        
                <div>
                    <h3 class="experience_title">{inf.name}</h3>
                    <span class="experience_subtitle">{inf.school}</span>
                    {#if inf.desc != ''}
                        <span class="experience_subtitle">{inf.desc}</span>
                    {/if}
                    <div class="experience_calendar">
                        <FontAwesomeIcon icon="calendar"/>
                        {inf.date}
                    </div>
                </div>
                
            </div>
        {/if}
    {/each}

    <div class="experience_data">
        <div></div>
        <div>
            <span class="experience_rounder"></span>
        </div>
    </div>

</div>