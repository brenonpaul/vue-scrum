<script>
import ListaTarefas from "./components/ListaTarefas.vue";
export default {
  components: { ListaTarefas },
  data() {
    return {
      titulo: "Kanban",
      tarefas: [
        {
          descricao: "treinar",
        },
        {
          descricao: "estudar",
        },
        {
          descricao: "jogar",
        },
      ],
    };
  } 
};
</script>
<template>
    <h1>{{ titulo }}</h1> 
    <main>
      <ListaTarefas title="To Do" :tarefas="tarefas"/>
      <ListaTarefas title="Done" :tarefas="tarefas"/>
    </main>
</template>

<style>
@import "./assets/base.css";

body {
  margin: 0;
  padding: 0;
  height: 100vh;
  background-color: powderblue;
  display: flex;
  justify-content: center;
  align-items: center;
}

main {
  width: 60vw;
  background-color: azure;
  height: 70vh;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-radius: 10px;
  padding: 1%;
}

h1 {
  text-align: center;
}

</style>
