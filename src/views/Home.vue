<template>
  <div id="container">
    <section>Expenses</section>
    <ul>
      <li v-for="expense in expenses">{{ expense }}</li>
    </ul>
  </div>
</template>

<script lang="ts">
import {ref} from "vue";
export default {
  name: 'Home',
  setup() {
    const expenses = ref([100, 200, 300])

    return {
      expenses
    }
  }
}
</script>

<style scoped>
#container{
  border: 2px solid #598C58;
  height: 100%;
  box-shadow: 0 10px 20px rgba(0,0,0,0.19);
  border-radius: 5px;
  background-color: #DDE8B3;
}

ul {
  list-style-type: none;
  padding: 0;
}
</style>
