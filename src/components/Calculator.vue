<template>
        <div v-show="result" id="result" class="alert alert-success" role="alert">
            O resultado é: {{ result }}
        </div>
        <form id="formAction" class="row gx-3 gy-2 align-items-center" @submit="calc">
                <div class="col-4">
                    <label for="number1" class="form-label">Número 1:</label>
                    <input class="form-control" type="number"  v-model="number1" min="0" id="number1">
                </div>
                <div class="col-4">
                    <label for="number2" class="form-label">Número 2:</label>
                    <input type="number" class="form-control" v-model="number2" min="0" id="number2">
                </div>
                <div class="col-4">
                    <label for="number2" class="form-label">Ação:</label>
                    <select class="form-select" v-model="action" id="action">
                        <option selected>Selecione uma opção</option>
                        <option value="sum" selected>Somar</option>
                        <option value="subtract">Subtrair</option>
                        <option value="multiply">Multiplicar</option>
                        <option value="divide">Dividir</option>
                    </select>
                </div>
                <div class="col-12">
                    <button class="btn btn-primary" type="submit">Calcular</button>
                </div>
        </form>
            <div id="result"></div>

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
                    this.result =  this.number1 * this.number2;
                    break;
                case "divide":
                    this.result =  this.number1 / this.number2;
                    break;
            }
        }
    }
}
</script>