<section id="keyboard">
    <button value ="7" on:click>7</button>
    <button value ="8" on:click>8</button>
    <button value ="9" on:click>9</button>
    <button value ="add" on:click>+</button>

    <button value ="4" on:click>4</button>
    <button value ="5" on:click>5</button>
    <button value ="6" on:click>6</button>
    <button value ="sub" on:click>-</button>

    <button value ="1" on:click>1</button>
    <button value ="2" on:click>2</button>
    <button value ="3" on:click>3</button>
    <button value ="mul" on:click>x</button>

    <button value ="comma" on:click>,</button> 
    <button value ="0" on:click>0</button>
    <button value ="enter" on:click>=</button>  
    <button value ="div" on:click>/</button>  

    <button value ="clear" style="grid-column: span 4" on:click>Clear</button> 
</section>

<style lang="scss">
    #keyboard {
        display:grid;
        height:100%;
    }

    button {
        font-size: 7rem;
        border-radius: 1rem;
    }

    button:hover{
        color: green;
        font-weight: bolder;
    } 
</style>