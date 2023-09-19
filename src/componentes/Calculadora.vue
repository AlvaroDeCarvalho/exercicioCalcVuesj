<script setup>
const props = defineProps(['numeroUm', 'numeroDois', 'operacaoTot','calcResultado','editNumero1', 'editNumero2', 'operacao'])
</script>

<template>
    <div class="body">
        <div class="container">
            <h1>Calculadora do Álvaro</h1>

            <div class="inputs">
                <input type="number" placeholder="Insira o primeiro número" :value="props.numeroUm" @change="props.editNumero1">
                <input type="number" placeholder="Insira o segundo número" :value="props.numeroDois" @change="props.editNumero2" >
                Escolha uma operação:
                <select :value="props.operacao" @change="props.operacaoTot">
                    <option value="multiplicacao">*</option>
                    <option value="divisao">/</option>
                    <option value="soma">+</option>
                    <option value="subtracao">-</option>
                </select>
                <p>Resultado: {{ props.calcResultado }}</p>
            </div>

        </div>
    </div>
</template>

<style scoped>
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    font-family: sans-serif;
}

.container {
    max-width: 960px;
    width: 100%;
    margin: 0px auto;
}

.container h1 {
    margin-bottom: 32px;
}

.inputs {
    width: 640px;
    align-items: center;
    display: block;
}

.inputs input {
    border-radius: 10px;
    border: 1px solid;
    margin-bottom: 16px;
    width: 100%;
    padding: 12px;

}
</style>