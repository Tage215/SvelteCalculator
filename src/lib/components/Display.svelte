<script>
    export let display;
</script>

<input type="text" id='display' disabled="disabled" value={display}>

<style lang="scss">
    #display {
        width: 100%;
        font-size: 10rem;
        background-color: black;
        color: limegreen;
        text-align: right;
        padding: 10px 4px 10px 4px;
        font-family: lcd;
        border: 1px solid limegreen;
        border-radius:4px;
    }
</style>