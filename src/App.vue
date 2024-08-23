<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue'
import Formulario from './components/Formulario.vue'
import Resultado from  './components/Resultado.vue'
import { parse } from 'vue/compiler-sfc';

const estado = reactive({
    campo1: '',
    campo2: '',
    operacao: 'somar',
    resultado: ''
});



const atualizarResultado = () => { 
    const {operacao} = estado //a operacao passa a ser =  estado para trabalhamos com switch e trocar pra +,-,*,/ e pra haver essa troca precisa do reactive por isso = estado pois estado repesenta reactive
        switch(operacao) {
        case 'subtrair':
        return parseFloat(estado.campo1) - parseFloat(estado.campo2)
        case 'multiplicar':
        return parseFloat(estado.campo1) * parseFloat(estado.campo2)
        case 'dividir':
        return parseFloat(estado.campo1) / parseFloat(estado.campo2)
        default:
        return parseFloat(estado.campo1) + parseFloat(estado.campo2) //caso natural pois começa com o + ou seja se n tiver nenhuma troca de operador fica a + msm
    }
};

//atualizarResultado();
</script>


<template>
    <div>
        <Cabecalho />
        <Formulario :operadores="evento=> estado.operacao= evento.target.value" :camPos1="evento=> estado.campo1 = evento.target.value" :camPos2="evento=> estado.campo2 = evento.target.value" />
        <Resultado  :camPos1="estado.campo1" :camPos2="estado.campo2" :resuTa="atualizarResultado()"/>
    </div>

</template> 

<style scoped></style>
