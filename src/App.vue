<script setup>
import {ref, computed} from 'vue'
const produtos = [
    {
        id: 1,
        nome: 'Camiseta',
        preco: 49.90,
        quantidade: 1
    },
    {
        id: 2,
        nome: 'Calça',
        preco: 99.90,
        quantidade: 1
    },
    {
        id: 3,
        nome: 'Meia',
        preco: 9.90,
        quantidade: 1
    },
    {
        id: 4,
        nome: 'Sapato',
        preco: 199.90,
        quantidade: 1
    },
    {
        id: 5,
        nome: 'Boné',
        preco: 29.90,
        quantidade: 1
    },
    {
        id: 6,
        nome: 'Óculos',
        preco: 99.90,
        quantidade: 1
    },
    {
        id: 7,
        nome: 'Relógio',
        preco: 299.90,
        quantidade: 1
    },
    {
        id: 8,
        nome: 'Bermuda',
        preco: 79.90,
        quantidade: 1
    },
    {
        id: 9,
        nome: 'Cueca',
        preco: 19.90,
        quantidade: 1
    },
    {
        id: 10,
        nome: 'Meia',
        preco: 9.90,
        quantidade: 1
    },
]
function incrementar() {
  quantidade.value++
}
function decrementar() {
    quantidade.value--
}

</script>

<template>
    <div v-for="produto in produtos" :key="produto.id">
        <p>{{ produto.name }}</p>
        <p>{{ produto.preco }}</p>
        <p>{{ produto.quantidade }}</p>
        <button @click="incrementar" {{ quantidade }}>+</button>
    </div>

</template>

<style scoped>

</style>
