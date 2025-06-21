<script>
	import Selector from './InlineSelector.svelte';
</script>

<main>
	<h1>Text mirror</h1>
	<Selector
		form={{
			message: {
				label: 'text',
				hint: 'Mirror',
				type: 'text'
			},
			recipient: {
				label: 'recipient',
				hint: 'to',
				type: 'select',
				options: {
					yourself: { label: 'yourself' },
					message_jar: { label: 'the message jar' }
				}
			},
			time: {
				label: 'time',
				hint: 'at',
				type: 'tangent_select',
				options: {
					specific: {
						label: 'a specific time',
						type: 'datetime-local'
					},
					within_interval: {
						label: 'any time within an interval',
						type: 'date_range'
					}
				}
			}
		}}
	></Selector>
</main>
