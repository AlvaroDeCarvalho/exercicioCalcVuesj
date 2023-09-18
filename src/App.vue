        <script setup>
        import { ref, reactive } from 'vue';
        
        const estado = reactive({
          numero1: '',
          numero2: '',
          operacao: 'multiplicacao',
        });
        
        const calcularResultado = () => {
          const num1 = parseFloat(estado.numero1);
          const num2 = parseFloat(estado.numero2);
          if (isNaN(num1) || isNaN(num2)) {
          return 'Erro: Insira números válidos';
        }
          const {operacao} = estado
          switch(operacao){
            case 'multiplicacao':
              return num1 * num2
            
            case 'soma':
              return num1 + num2

            case 'subtracao':
              return num1 - num2
            
            case 'divisao':
              return num1 / num2

            default:
              return 'operação invalida'
          }
        }
        </script>
        
<template>
  <div class="body">
    <div class="container">
      <h1>Calculadora do Álvaro</h1>

      <div class="inputs">
        <input  type="number" placeholder="Insira o primeiro número" v-model="estado.numero1">
        <input  type="number" placeholder="Insira o segundo número" v-model="estado.numero2">
        Escolha uma operação:
        <select   v-model="estado.operacao">
          <option value="multiplicacao">*</option>
          <option value="divisao">/</option>
          <option value="soma">+</option>
          <option value="subtracao">-</option>
        </select>
        <p>Resultado: {{ calcularResultado() }}</p>
      </div>

    </div>
  </div>
</template>



<style scoped>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: sans-serif;
}
.container{
    max-width: 960px;
    width: 100%;
    margin: 0px auto;
}
.container h1{
  margin-bottom: 32px;
}
.inputs{
  width: 640px;
  align-items: center;
  display: block;
}
.inputs input{
  border-radius: 10px;
  border: 1px solid ;
  margin-bottom: 16px;
  width: 100%;
  padding: 12px;

}
</style>
