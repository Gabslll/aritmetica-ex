<script setup>
const props = defineProps(['numero1', 'numero2', 'operacao'])
</script>

<template>
    <div class="row">
        <div class="col-md-2 mt-4">
            <input @keyup="props.numero1" type="number" required class="form-control mb-2"
                placeholder="Insira um número aqui">
            <input @keyup="props.numero2" type="number" required class="form-control"
                placeholder="Insira um número aqui">
        </div>
        <div class="col-md-2 mt-4">
            <select @change="props.operacao" class="form-control">
                <option value="+">Somar</option>
                <option value="-">Subtrair</option>
                <option value="*">Multiplicar</option>
                <option value="/">Divisão</option>
            </select>
        </div>
    </div>
</template>