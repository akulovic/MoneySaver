<template>
  <form id="container">
    <div>
      <label for="expenseTitle">Expense Title</label>
      <select id="expenseTitle" name="expenseTitle" v-model="expenseTitle">
        <option>Food</option>
        <option>Gas</option>
        <option>Housing</option>
      </select>
    </div>
    <div>
      <label for="expenseAmount">Expense Amount</label>
      <input id="expenseAmount" type="text" v-model="expenseAmount">
    </div>
    <div>
      <label for="expenseDate">Expense Date</label>
      <input id="expenseDate" type="date" v-model="expenseDate">
    </div>
    <button @click="enterExpense" type="submit">Enter</button>
  </form>
</template>

<script lang="ts">
import {ref} from "vue";

export default {
  name: "InputField",

  emits: ['expenseEntered'],

  setup(props: any, context: any){
    const expenseTitle = ref('')
    const expenseAmount = ref(0)
    const expenseDate = ref(new Date())

    function enterExpense(event: any) {
      if (expenseTitle.value && expenseAmount.value && expenseDate.value){
        event.preventDefault()
        const expense = {
          cost: expenseAmount.value,
          category: expenseTitle.value,
          date: expenseDate.value
        }
        context.emit('expenseEntered', expense)
        // reset form
        expenseTitle.value = ''
        expenseAmount.value = 0
        expenseDate.value = new Date()
      }
    }

    return {
      expenseTitle,
      expenseAmount,
      expenseDate,
      enterExpense
    }
  }
}
</script>

<style scoped>
#container {
  margin: 10px;
  padding: 10px;
  width: 40%;
}

label {
  font-weight: bold;
  margin-right: 5px;
  float: left;
}

input, select {
  width: 50%;
}

button {
  padding: 2px 15px 2px 15px;
  margin-top: 5px;
  color: white;
  background-color: #598C58;
  border: 2px solid #598C58;
  border-radius: 5px;
}
</style>