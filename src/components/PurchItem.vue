<template>
    <tr v-for="buy in purchases[today]" :key="buy.id">
        <td>{{buy.name}}</td>
        <td>{{buy.category}}</td>
        <td>{{buy.cost}}</td>
        <button>edit</button>
        <button>delete</button>
    </tr>
</template>
<script>
export default {
props:{
    purchases:Object,
    today:Function,
}
}
</script>
<style scoped>

</style>