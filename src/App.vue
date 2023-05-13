<script setup>
import { ref, computed } from 'vue'
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
const carrinho = ref({
    itens: [],
    total: 0,
})
function addCarrinho(index) {
    carrinho.value.produtos.push({
        id: carrinho.value.length + 1,
        nome: produtos.value[index].nome,
        preco: produtos.value[index].preco,
        quantidade: 1,
        valorTotal: produtos.value[index].preco * 1
    })
    carrinho.value.total += produtos.value[index].preco * 1
}
function incrementar(index) {
    produtos[index].quantidade++
}
function decrementar(index) {
    produtos.value.splice(index, 1)
}
function remover(index) {
    carrinho.value.total = carrinho.value.total - carrinho.value.produtos[index].valorTotal
    carrinho.value.produtos.splice(index, 1)
}

</script>

<template>
    <div class="arrayProdutos">
        <div class="produtos" v-for="produto in produtos">
            <p>{{ produto.id }}- {{ produto.nome }}</p>
            <p>Preço: {{ produto.preco }}</p>
            <p>Quantidade: {{ produto.quantidade }}</p>
            <div>
                <button class="botaoDec" @click="decrementar(index)">-</button>
                <button class="botaoInc" @click="incrementar(index)">+</button>
                <button class="botaoAdd" @click="addCarrinho(index)">Adicionar</button>
            </div>
        </div>
    </div>
    <hr>
    <button class="botCarrinho" @click="listCarrinnho">Ver carrinho</button>
    <div class="listCarrinho">
        <div class="carrinho" v-for="(item, index) in carrinho.produtos"> {{ produto.nome }} - {{
            produto.valorTotal.toFixed(2) }} >
            <button @click="incrementar(index)">+</button>
            {{ produto.quantidade }}
            <button @click="decrementar(index)">-</button>
            <button @click="remover(index)">Remover</button>
            <button class="produtos">Ver produtos</button>
        </div>
    </div>
</template> 

<style scoped>
.arrayProdutos {
    display: grid;
    grid-template-columns: 1fr 1fr;
    width: 60%;
    margin: auto;
    gap: 20px;
    font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.produtos {
    display: flex;
    flex-direction: column;
    align-items: center;
    border-radius: 10px;
    color: aliceblue;
    background-image:linear-gradient(to right, rgb(72, 9, 80), rgb(0, 0, 0));
    margin-top: 1%;
    margin-left: 5%;
    margin-right: 5%;
}

.botaoDec {
    color: rgb(255, 255, 255);
    background-color: rgb(0, 0, 0);
    margin-bottom: 10px;
    border-radius: 10px;
}

.botaoInc {
    color: rgb(255, 255, 255);
    background-color: rgb(0, 0, 0);
    margin-bottom: 10px;
    border-radius: 10px;
}

.botaoAdd {
    color: rgb(255, 255, 255);
    background-color: rgb(0, 0, 0);
    margin-top: 5%;
    margin-bottom: 10px;
    border-radius: 10px;
}

.botCarrinho {
    display: flex;
    flex-direction: column;
    align-items: center;
    border-radius: 10px;
    color: aliceblue;
    background-image:linear-gradient(to right, rgb(72, 9, 80), rgb(0, 0, 0));
    margin-top: 1%;
    margin-left: 5%;
    margin-right: 5%;
}
.listCarrinho{
    display: grid;
    grid-template-columns: 1fr 1fr;
    width: 60%;
    margin: auto;
    gap: 20px;
    font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>
