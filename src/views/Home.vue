<template>
  <div id="container">
    <section>Expenses</section>
    <ul>
      <li v-for="expense in expenses">${{ expense.cost }} - {{ expense.category }}</li>
    </ul>
    <input-field @expenseEntered="expenseEntered"></input-field>
    <div>Hello</div>
  </div>
</template>

<script lang="ts">
import {ref} from "vue";
import InputField from "@/components/InputField.vue";
export default {
  name: 'Home',
  components: {InputField},
  setup() {
    const expense1 = {
      cost: 100,
      category: 'Food'
    }

    const expense2 = {
      cost: 200,
      category: 'Gas'
    }

    const expense3 = {
      cost: 300,
      category: 'Housing'
    }

    const expenses = ref([expense1, expense2, expense3])

    function expenseEntered(expense: any){
      expenses.value.push(expense)
    }

    return {
      expenses,
      expenseEntered
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

section {
  font-weight: bold;
}
</style>
