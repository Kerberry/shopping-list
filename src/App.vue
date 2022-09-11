<template>
  <PurchForm 
    :categories="categories"
    @addPurchase = 'addPurchase'
  />
  <table>
    <thead>
      <tr>
        <td>название</td>
        <td>категория</td>
        <td>стоимость</td>
      </tr>
    </thead>
    <tbody>
      <PurchItem
        :purchases="purchases"
        :today="today"
      />
    </tbody>
    <tfoot>
      <tr>
        <td colspan="2">итого:</td>
        <td></td>
      </tr>
    </tfoot>
  </table>
  <PurchItem
  />
</template>

<script>
import PurchForm from "./components/PurchForm.vue";
import PurchItem from "./components/PurchItem.vue";
export default {
  name: "App",
  components: {
    PurchForm,
    PurchItem,
  },
  data() {
    return {
      purchases:{},
      categories:[],
      today:new Date().getFullYear()+''+new Date().getMonth()+new Date().getDate(),
    };
  },
  methods: {
    addPurchase(name, category, cost) { 
      if(!this.purchases[this.today]){
        this.purchases[this.today]=[];
      }
      this.purchases[this.today].push({name: name, category: category, cost:cost});
      if(!this.categories.includes(category)){
        this.categories.push(category);
      }
      window.localStorage.setItem('purchases', JSON.stringify(this.purchases));    
      console.log(this.today)
    },
  },
  created:function(){
    this.purchases = JSON.parse(window.localStorage.getItem('purchases'))?JSON.parse(window.localStorage.getItem('purchases')):{};
  }
  
};
</script>

<style>
</style>