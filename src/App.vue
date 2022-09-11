<template>
  <PurchForm />
</template>

<script>
import PurchForm from "./components/PurchaseForm.vue";
export default {
  name: "App",
  components: {
    PurchForm,
  },
  data() {
    return {
      purchases:[],
      categories:[],
    };
  },
  methods: {
    addPurch(name, category, cost) {
      this.purchases.push({name: name, category: category, cost:cost});
      this.categories.push(category);
      console.log(this.purchases);
      console.log(this.categories)
    },
  },
};
</script>

<style>
</style>