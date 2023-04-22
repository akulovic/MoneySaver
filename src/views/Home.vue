<template>
  <div id="container">
    <div id="form-container">
      <h4>Expense Form</h4>
      <input-field style="height: 20%" @expenseEntered="expenseEntered"></input-field>
    </div>
    <div id="card-container">
      <h4>Expenses</h4>
      <div v-for="expense in expenses">
        <Card :title="expense.category" :date="expense.date" :item="expense.item" :amount="expense.cost"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import {ref} from "vue";
import InputField from "@/components/InputField.vue";
import Card from "@/components/Card.vue";
export default {
  name: 'Home',
  components: {Card, InputField},
  setup() {
    const expense1 = {
      cost: 100,
      category: 'Food',
      item: 'Chips',
      date: '3/22/2023'
    }

    const expense2 = {
      cost: 200,
      category: 'Gas',
      item: 'Petrol',
      date: '3/23/2023'
    }

    const expense3 = {
      cost: 300,
      category: 'Housing',
      item: 'Rent',
      date: '4/11/2013'
    }

    const expenses = ref([expense1, expense2, expense3])

    function expenseEntered(expense: any){
      expense.date = new Date(expense.date).toLocaleDateString('en-US')
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
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}

@media screen and (max-width: 700px) {
  #container{
    flex-direction: column;
    align-items: center;
  }
}

#form-container{
  width: 45%;
  float: left;
}

#card-container{
  width: 45%;
  float: right;
}

section {
  font-weight: bold;
  font-size: large;
}
</style>
