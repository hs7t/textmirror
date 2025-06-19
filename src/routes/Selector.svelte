<script>
	import { get } from "svelte/store";

    let { form } = $props();
    function getEntries(obj) { return Object.entries(obj) };
    let formAnswer = {}

    for (let [key, input] of getEntries(form)) {
        if (input["type"] === "tangent_select") {
            for (let [key, input] of getEntries(form)) {
                
            }
        } else {
            formAnswer[key];
        }
    }
</script>


<div>
    {#each getEntries(form) as [key, input]}
        {input["lead"]}
        {#if input["type"] === "text"}
            <input type="text" id={key}>
        {:else if input["type"] === "select"}
            <select id={key}>
                {#each input["options"] as option}
                    <option>{option}</option>
                {/each}
            </select>
        {:else if input["type"] === "tangent_select"}
            <select id={key}>
                {#each getEntries(input["options"]) as [key, tangent]}
                    <option id={key}>{tangent["name"]}</option>
                {/each}
            </select>
        {/if}
    {/each}
</div>