<template>
  <form>
    <input v-model="newName" placeholder="Название"/>
    <input v-model="newCategory" placeholder="Категория"/>
    <input v-model="newCost" type="number" placeholder="Цена"/>
    <button @click="$emit('addPurch', newName, newCategory, newCost)">add</button>
  </form>
</template>

<script>
export default {
  name: "PurchForm",
  data(){
    return{
      newName:'',
      newCategory:'',
      newCost:''
    }
  },
  
};
</script>

<style scoped>
</style>