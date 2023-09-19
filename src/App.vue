        <script setup>

        import { ref, reactive } from 'vue';
        import Calculadora from './componentes/calculadora.vue'
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

        console.log(estado.numero1)
        </script>
        
<template>
  <Calculadora
  :numeroUm=" estado.numero1 "
  :editNumero1="evento => estado.numero1 = evento.target.value"
  :editNumero2="evento => estado.numero2 = evento.target.value"
  :numeroDois=" estado.numero2 "
  :operacao="estado.operacao"
  :operacaoTot="evento => estado.operacao = evento.target.value"
  :calcResultado="calcularResultado()"
  />
</template>