<script setup>
    const props = defineProps(['numero1', 'numero2', 'result' ])
</script>

<template>
    <span v-if="props.numero1 && props.numero2 != ''"><h2 class="mt-2 ms-2">Resultado: {{ props.result }}</h2></span>
    <span v-else-if="props.numero1 || props.numero2 === ''"><h2 class="mt-2 ms-2">Digite os dois números</h2></span>
</template>