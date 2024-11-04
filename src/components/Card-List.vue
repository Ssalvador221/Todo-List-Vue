<template>
  <div class="container">
    <div class="card">
      <div class="card-header">
        <label for="title"> Título da Tarefa</label>
        <input type="text" v-model="title" placeholder="Enter Todo" />
        <button type="submit" @click="onclick">Add</button>
      </div>
      <div class="card-list">
        <ul v-for="(title, index) in list" :key="index">
          <li>{{ title }}</li>
        </ul>
      </div>
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
