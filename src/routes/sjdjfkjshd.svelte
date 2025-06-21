{#if input.type === 'tangent_select'}
    {#each getEntries(input.options) as [tangent_key, tangent]}
        {#if formAnswer[key] == tangent_key} 
            {#if tangent.type === 'datetime-local'} 
                <input type="datetime-local">
            {:else if tangent.type === 'date_range'}
                <DateRangePicker 
                    bind:date_range={formAnswer[key]} 
                />
            {/if}
        {/if}
    {/each}
{/if}