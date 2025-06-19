<script>
    import Selector from "./Selector.svelte";
</script>

<main>
    <h1>Text mirror</h1>
    <Selector form={{
        "message": {
            "name": "Text",
            "lead": "Mirror",
            "type": "text"
        },
        "recipient": {
            "name": "Recipient",
            "lead": "to",
            "type": "select",
            "options": [
                "Yourself",
                "Anyone"
            ]
        },
        "time" : {
            "name": "Time",
            "type": "tangent_select",
            "options": {
                "specific": {
                    "name": "At a specific time",
                    "type": "date"
                },
                "within_interval": {
                    "name": "Sometime within an interval",
                    "type": "date_range"
                }
            }
        },
    }}></Selector>
</main>