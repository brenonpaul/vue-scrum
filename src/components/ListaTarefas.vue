<script>
export default {
    props: {
        title: {
            type: String,
        },
        tarefas: {
            type: Object,
            default: [],
        },
        realizadas: {
            type: Object,
            default: [],
        }
    },
    methods: {
        concluirTarefa(id) {
            this.$emit("concluirTarefa", id);
        },
        refazerTarefa(id) {
            this.$emit("refazerTarefa", id);
        }
    } 
};
</script>
<template>
    <article>
        <h2>{{ title }}</h2>
        <section v-if="this.title === 'To Do'">
            <div v-for="(tarefa, index) in tarefas" :key="index" class="box">
                <h3> {{ tarefa.descricao }} </h3>
                <button @click="concluirTarefa(index)" class="btn first" id="concluir">Concluir</button>
            </div>
        </section>
        <section v-else>
            <div v-for="(realizada, index) in realizadas" :key="index" class="box">
                <h3>{{ realizada.descricao }}</h3>
                <button @click="refazerTarefa(index)" class="btn first" id="desfazer">Desfazer</button>
            </div>
        </section>
    </article>
</template>
<style>
article {
    width: 45%;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: auto;
}
section {
    background-color: rgb(209, 246, 115);
    width: 100%;
    min-height: 50vh;
    height: auto;
    border-radius: 5px;
}
.box {
    border-bottom: 1px solid rgb(64, 106, 112);
    display: flex;
    justify-content: space-between;
    padding: 3%;
}
h3 {
    font-size: 120%;
}
#concluir {
    border: 1px solid #5fa786;
    color: #1c6142;
}
#concluir:hover {
    box-shadow: 0 0 40px 40px #5fa786 inset;
    color: #fff;
    outline: 0;
}
#desfazer {
    border: 1px solid #e74c3c;
    color: #e74c3c;
}
#desfazer:hover {
    box-shadow: 0 0 40px 40px #e74c3c inset;
    color: #fff;
    outline: 0;
}
.btn {
    box-sizing: border-box;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background-color: transparent;
    border-radius: 0.6em;
    cursor: pointer;
    display: -webkit-box;
    display: -webkit-flex;
    display: -ms-flexbox;
    display: flex;
    -webkit-align-self: center;
    -ms-flex-item-align: center;
    align-self: center;
    font-size: 1rem;
    font-weight: 400;
    line-height: 1;
    padding: 2%;
    text-decoration: none;
    text-align: center;
    font-family: 'Montserrat', sans-serif;
}

.first {
    -webkit-transition: box-shadow 300ms ease-in-out, color 300ms ease-in-out;
    transition: box-shadow 300ms ease-in-out, color 300ms ease-in-out;
}
.first:hover {
    box-shadow: 0 0 40px 40px #5fa786 inset;
}
</style>