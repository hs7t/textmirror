<script>
	import { get } from 'svelte/store';
	import DateRangePicker from './DateRangePicker.svelte';

	let { form } = $props();
	function getEntries(obj) {
		return Object.entries(obj);
	}
	let formAnswer = $state({});
	let placeholder;
</script>

<div>
	{#each getEntries(form) as [key, input]}
		<span>{input.lead}</span>
		{#if input.type === 'text'}
			<input type="text" id={key} placeholder={input.name} />
		{:else if ((input.type === 'select') || (input.type === 'tangent_select'))}
			<select bind:value={formAnswer[key]} id={key}>
				<option disabled value="">{input.name}</option>

				{#each getEntries(input.options) as [option_key, option]}
					<option value={option_key}>{option.name}</option>
				{/each}
			</select>

			{#if input.type === 'tangent_select'}
				{#each getEntries(input.options) as [tangent_key, tangent]}
					{#if formAnswer[key] == tangent_key} 
						{#if tangent.type === 'datetime-local'} 
							<input type="datetime-local">
						{:else if tangent.type === 'date_range'}
							<DateRangePicker 
								bind:date_range={placeholder} 
							/>
						{/if}
					{/if}
				{/each}
			{/if}
		{/if}
	{/each}
</div>
