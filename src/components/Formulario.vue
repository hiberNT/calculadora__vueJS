<script setup>
const props = defineProps(['camPos1','camPos2','operadores'])
</script>

<template>
    <form class="container mt-5">
        <div class="row justify-content-center">
            <div class="col-auto">
                <input @keyup="props.camPos1" required type="number" class="form-control mb-2" placeholder="Digite um número"><!--keyup ja armazena em camPo1 oq o usuario digitar-->
            </div>
            <div class="col-auto">
                <input @keyup="props.camPos2" required type="number" class="form-control mb-2" placeholder="Digite um número"> <!--o @input é para escutar registar o evento de atualizarResultado-->
            </div>
            <div class="col-auto">
                <select class="form-control" @change="props.operadores">
                    <option value="somar">Somar</option>
                    <option value="subtrair">Subtrair</option>
                    <option value="multiplicar">Multiplicação</option>
                    <option value="dividir">Divisão</option>
                </select>
            </div>
            <div class="mt-5 col-7 ">
                <!--<input :value="props.resuTa" class="form-control text-center" placeholder="RESULTADO" >-->
            </div>
        </div>
    </form>
</template>