<template>
    <div class="card">
      <div class="card-header">
        <label for="title"> Título da Tarefa</label>
        <input type="text" v-model="title" placeholder="Enter Todo" />
        <button type="submit" @click="onclick">Add</button>
      </div>
      <div class="card-list">
        <h2>Lista de Tarefas</h2>
        <ul v-for="(title, index) in list" :key="index">
          <li>{{ title }}</li>
          <button class="btn-delete" @click="list.splice(index, 1)">X</button>
        </ul>
      </div>
    </div>
</template>

<script>
import { ref } from 'vue'
const list = ref([])
const title = ref('')

export default {
  name: 'CardList',
  setup() {
    const onclick = () => {
      list.value.push(title.value)
      title.value = ''
    }
    return { list, title, onclick }
  }

}


</script>

<style lang="css" scoped>

  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    margin-top: 40px;
  }

  .card {
    background-color: rgb(243, 182, 126);
    width: 700px;
    padding: 30px;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .card-header {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .card-list {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 20px;
    gap: 10px;
  }

  .card-list ul {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 10px;
  }

  .card-list li {
    color: white;
    font-family: 'Courier New', Courier, monospace;
    font-size: 20px;
    font-weight: 700;
    text-align: center;
  }

  .card-list h2 {
    color: white;
    font-family: 'Courier New', Courier, monospace;
    font-size: 25px;
    font-weight: 700;
    text-align: center;
  }

  .btn-delete {
    background-color: transparent;
    border-radius: 5px;
    color: white;
    font-family: 'Courier New', Courier, monospace;
    font-size: 12px;
    font-weight: 700;
    border-radius: 5px;
    width: 30px;
    border: 1px solid rgb(210, 143, 50);
    padding: 5px;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .btn-delete:hover {
    background-color: rgb(210, 143, 50);
  }

  input {
    width: 250px;
    padding: 8px;
    border-radius: 5px;
    border: 1px solid rgb(243, 182, 126);
    font-size: 16px;
    margin: 5px 0;
    outline: none;
  }

  button {
    width: 100px;
    padding: 8px;
    border-radius: 5px;
    border: 1px solid rgb(243, 182, 126);
    font-size: 16px;
    margin: 5px 0;
    outline: none;
  }

  label {
    font-size: 18px;
    font-weight: 700;
    color: white;
    font-family: 'Courier New', Courier, monospace;
  }

</style>
