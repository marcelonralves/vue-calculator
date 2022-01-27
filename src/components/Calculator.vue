<template>
    <form id="formAction" @submit="calc">
        <label for="number1">Número 1:</label>
        <input type="number"  v-model="number1" min="0" id="number1"><br>
        <label for="number2">Número 2:</label>
        <input type="number" v-model="number2" min="0" id="number2"><br>
        <select v-model="action" id="action"><br>
            <option value="sum" selected>Somar</option>
            <option value="subtract">Subtrair</option>
            <option value="multiply">Multiplicar</option>
            <option value="divide">Dividir</option>
        </select><br>
        <button type="submit">Calcular</button>
    </form>
        <div id="result">{{ result }}</div>
</template>

<script>
export default {
    name: 'Calculator',

    data() {
        return {
            number1 : null,
            number2 : null,
            action : null,
            result : null,
        }
    },


    methods: {
        calc(e) {
            e.preventDefault();

            switch(this.action) {
                case "sum":
                    this.result = this.number1 + this.number2;
                    break;
                case "subtract":
                    this.result = this.number1 - this.number2;
                    break;
                case "multiply":
                    this.result =  this.number1 / this.number2;
                    break;
                case "divide":
                    this.result =  this.number1 * this.number2;
                    break;
            }
        }
    }
}
</script>
