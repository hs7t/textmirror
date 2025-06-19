<script>
	import Selector from './InlineSelector.svelte';
</script>

<main>
	<h1>Text mirror</h1>
	<Selector
		form={{
			message: {
				name: 'text',
				lead: 'Mirror',
				type: 'text'
			},
			recipient: {
				name: 'recipient',
				lead: 'to',
				type: 'select',
				options: {
					yourself: {
						name: 'yourself'
					},
					message_jar: {
						name: 'the message jar'
					}
				}
			},
			time: {
				name: 'time',
				lead: 'at',
				type: 'tangent_select',
				options: {
					specific: {
						name: 'a specific time',
						type: 'datetime-local'
					},
					within_interval: {
						name: 'any time within an interval',
						type: 'date_range'
					}
				}
			}
		}}
	></Selector>
</main>
