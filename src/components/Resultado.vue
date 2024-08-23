<script setup>
    const props = defineProps(['camPos1','camPos2','resuTa'])
</script>

<template>
    <span class="text-center" v-if="props.camPos1 && props.camPos2 !='' "> <h2>Resultado: {{ props.resuTa }} </h2></span>
    <span class="text-center" v-else-if="props.camPos1 || props.camPos2 === ''"><h2>Digite os dois numeros</h2></span>
</template>