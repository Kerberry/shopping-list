<template>
    <input v-model="newName" placeholder="Название"/>
    <input v-model="newCategory" placeholder="Категория" list="names"/>
    <datalist id="names">
      <option v-for="category in categories" :key="category.id">{{category}}</option>      
    </datalist>
    <input v-model="newCost" type="number" step="0.01" placeholder="Стоимость"/>
    <button @click="add">add</button>
</template>

<script>
export default {
  name: "PurchForm",
  props:{
    categories: Array,
  },
  emits:['addPurchase'],
  data(){
    return{
      newName:'',
      newCategory:'',
      newCost:''
    }
  },
  methods:{
    add(){
      this.$emit('addPurchase', this.newName, this.newCategory, this.newCost);
      this.newName='';
      this.newCategory='';
      this.newCost='';
    }
  }
  
};
</script>

<style scoped>
</style>