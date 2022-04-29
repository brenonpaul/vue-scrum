<script>
import ListaTarefas from "./components/ListaTarefas.vue";
export default {
  components: { ListaTarefas },
  data() {
    return {
      titulo: "Kanban",
      tarefas: [
        {
          descricao: "Algoritmo para escolha de turmas",
        },
        {
          descricao: "Revisar protocolo de segurança do servidor antigo",
        },
        {
          descricao: "Conversar com clientes sobre manutenção do sistema",
        },
      ],
      realizadas: [
        {
          descricao: "Reunião com novos sócios da empresa ",
        },
        {
          descricao: "Criação de banco de dados para sistema educional",
        },
      ],
    };
  },
  methods: {
    concluirTarefa(id){
      this.realizadas.push({descricao: this.tarefas[id].descricao});
      this.tarefas.splice([id],  1);
    },
    refazerTarefa(id) {
      this.tarefas.push({descricao: this.realizadas[id].descricao});
      this.realizadas.splice([id], 1);
    },
    adicionarTarefa(desc) {
      if(desc === '')
        return;
      this.tarefas.push({descricao: desc});
    }
  } 
};
</script>
<template>
  <h1>{{ titulo }}</h1> 
  <main>
    <ListaTarefas title="To Do" :tarefas="tarefas" @concluirTarefa="concluirTarefa" @adicionarTarefa="adicionarTarefa" />
    <ListaTarefas title="Done" :realizadas="realizadas" @refazerTarefa="refazerTarefa" />
  </main>
</template>
<style>
@import "./assets/base.css";

body {
  margin: 0;
  padding: 0;
  height: 100vh;
  background-color: #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
}
main {
  width: 60vw;
  background-color: rgb(35, 149, 149);
  height: 70vh;
  height: auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-radius: 10px;
  padding: 1%;
}
h1 {
  text-align: center;
  color: rgb(4, 89, 89);;
}
</style>
