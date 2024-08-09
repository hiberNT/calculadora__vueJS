<script setup>
const props = defineProps(['atualizaRes','resuTa','camPos1','camPos2','operadores'])
</script>

<template>
    <form class="container mt-5">
        <div class="row justify-content-center">
            <div class="col-auto">
                <input @input="props.atualizaRes" v-model.number="props.camPos1" type="number" class="form-control mb-2" placeholder="Digite um número"><!--v-model faz com q meu input seja o representado pelo o estado.campo1 ou seja tudo q digitar nesse input é armazenado nesse campo1-->
            </div>
            <div class="col-auto">
                <input @input="props.atualizaRes" v-model.number="props.camPos2" type="number" class="form-control mb-2" placeholder="Digite um número"> <!--o @input é para escutar registar o evento de atualizarResultado-->
            </div>
            <div class="col-auto">
                <select class="form-control" v-model="props.operadores" @change="props.atualiza">
                    <option value="somar">Somar</option>
                    <option value="diminuir">Subtrair</option>
                    <option value="multiplicar">Multiplicação</option>
                    <option value="dividir">Divisão</option>
                </select>
            </div>
            <div class="mt-5 col-7 ">
                <input :value="props.resuTa" class="form-control text-center" placeholder="RESULTADO" >
            </div>
        </div>
    </form>
</template>