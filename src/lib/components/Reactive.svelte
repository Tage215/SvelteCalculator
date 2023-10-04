<script>
    import Display from "$lib/components/Display.svelte";
    import Keyboard from "$lib/components/Keyboard.svelte";

    let display = "";
    let arithmetic = [];
    let numbers = [];
    let index = 0;
    let lastNumber = false;

    function click(e) {
        let btn = e.target.value;

        if (!isNaN(btn)) {
            addDigit(btn);
        } else {
            switch (btn) {
                case "comma":
                    addComma();
                    break;

                case "enter":
                    calculate();
                    break;

                case "clear":
                    memClear();
                    break;

                case "add":
                    setOperator("+");
                    break;

                case "sub":
                    setOperator("-");
                    break;

                case "mul":
                    setOperator("*");
                    break;

                case "div":
                    setOperator("/");
            }
        }
    }

    function addDigit(digit) {
        if (numbers[index] == null) {
            numbers[index] = digit;
            display = digit;
        } else {
            display += digit;
            numbers[index] += digit;
        }
        lastNumber = true;
    }

    function addComma() {
        if (numbers[index] != null && lastNumber) {
            display += ".";
            numbers[index] += ".";
            lastNumber = false;
        }
    }

    function setOperator(operator) {
        if(lastNumber){
            display = "";
            arithmetic[index] = operator;
            index++;
            lastNumber = false;
        }
    }

    function calculate() {
        let result = parseFloat(numbers[0]);
        let number = 0;
        for (let i = 0; i < arithmetic.length; i++) {
            number = parseFloat(numbers[i + 1]);
            switch (arithmetic[i]) {
                case "+":
                    result += number;
                    break;

                case "-":
                    result -= number;
                    break;

                case "*":
                    result *= number;
                    break;

                case "/":
                    result /= number;
            }
        }

        result = Math.round(result * 10000) / 10000;

        numbers = [];
        arithmetic = [];
        index = 0;

        if (result != null) {
            display = result;
            numbers[index] = result;
        }
    }

    function memClear() {
        display = null;
        arithmetic = [];
        numbers = [];
        index = 0;
    }
</script>

<Display {display} />
<Keyboard on:click={click} />
