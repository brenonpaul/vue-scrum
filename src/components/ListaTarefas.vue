<script>
export default {
    props: {
        title: {
            type: String,
        },
        tarefas: {
            type: Object,
            default: [],
        }
    }
};
</script>
<template>
    <article>
        <h2>{{ title }}</h2>
        <section>
            <div v-for="(tarefa, index) in tarefas" :key="index">{{tarefa.descricao}}
            <button>ok</button>
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
}
section {
    background-color: rgb(127, 207, 218);
    width: 100%;
    height: 50vh;
    border-radius: 5px;
}
</style>