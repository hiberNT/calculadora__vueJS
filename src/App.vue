<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue'
import Formulario from './components/Formulario.vue'

const estado = reactive({
    campo1: '',
    campo2: '',
    operacao: 'somar',
    resultado: ''
});

const somar = () => Number(estado.campo1) + Number(estado.campo2);
const subtrair = () => Number(estado.campo1) - Number(estado.campo2);
const multiplicar = () => Number(estado.campo1) * Number(estado.campo2);
const dividir = () => Number(estado.campo2) !== 0 ? Number(estado.campo1) / Number(estado.campo2) : 'Erro';

const atualizarResultado = () => {
    switch (estado.operacao) {
        case 'somar':
            estado.resultado = somar();
            break;
        case 'diminuir':
            estado.resultado = subtrair();
            break;
        case 'multiplicar':
            estado.resultado = multiplicar();
            break;
        case 'dividir':
            estado.resultado = dividir();
            break;
    }
};

//atualizarResultado();
</script>


<template>
    <div>
        <Cabecalho />
        <Formulario :operadores="estado.operacao" :camPos1="estado.campo1" :camPos2="estado.campo2" :atualizaRes="atualizarResultado" :resuTa= "estado.resultado"/>
    </div>

</template>

<style scoped></style>
