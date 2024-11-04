<template>
    <div class="card">
      <div class="card-header">
        <h1>Todo - List</h1>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Card-Header',
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
  }

  .card-header {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .card-header h1 {
    font-size: 40px;
    padding-left: 20px;
    color: white;
    font-family: monospace;
    font-weight: 400;
  }


</style>
