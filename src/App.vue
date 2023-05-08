<script setup>
import {ref, computed} from 'vue'
const produtos = [
    {
        id: 1,
        nome: 'Camiseta',
        preco: 49.90
    },
    {
        id: 2,
        nome: 'Calça',
        preco: 99.90
    },
    {
        id: 3,
        nome: 'Meia',
        preco: 9.90
    },
    {
        id: 4,
        nome: 'Sapato',
        preco: 199.90
    },
    {
        id: 5,
        nome: 'Boné',
        preco: 29.90
    },
    {
        id: 6,
        nome: 'Óculos',
        preco: 99.90
    },
    {
        id: 7,
        nome: 'Relógio',
        preco: 299.90
    },
    {
        id: 8,
        nome: 'Bermuda',
        preco: 79.90
    },
    {
        id: 9,
        nome: 'Cueca',
        preco: 19.90
    },
    {
        id: 10,
        nome: 'Meia',
        preco: 9.90
    }
]
const carrinho = [
    items: [
    {
      id: 1,
      nome: 'Camiseta',
      preco: 49.90,
      quantidade: 1,
      valorTotal: 49.90
    },
    {
      id: 2,
      nome: 'Calça',
      preco: 99.90,
      quantidade: 2,
      valorTotal: 199.80
    },
    {
      id: 3,
      nome: 'Meia',
      preco: 9.90,
      quantidade: 4,
      valorTotal: 39.60
    }
    {
      id: 4,
      nome: 'Sapato',
      preco: 199.90
      quantidade: 4,
      valorTotal: 39.60
    },
    {
        id: 5,
        nome: 'Boné',
        preco: 29.90
        quantidade: 4,
        valorTotal: 39.60
    },
    {
        id: 6,
        nome: 'Óculos',
        preco: 99.90
        quantidade: 4,
        valorTotal: 39.60
    },
    {
        id: 7,
        nome: 'Relógio',
        preco: 299.90
        quantidade: 4,
        valorTotal: 39.60
    },
    {
        id: 8,
        nome: 'Bermuda',
        preco: 79.90
        quantidade: 4,
        valorTotal: 39.60
    },
    {
        id: 9,
        nome: 'Cueca',
        preco: 19.90
        quantidade: 4,
        valorTotal: 39.60
    },
    {
        id: 10,
        nome: 'Meia',
        preco: 9.90
        quantidade: 4,
        valorTotal: 39.60
    }
    ]
    total: 288.30
]
</script>

<template>
  <ul>
    <li v-for="(produto, index) in produtos" :key="index"> {{ produto }} </li>
  </ul>
  <p v-for="(produto, index) in produtos" :key="index">{{ produto }}</p>
</template>

<style scoped>

</style>
