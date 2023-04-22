<template>
  <div id="card">
    <h2>{{ $props.title }}</h2>
    <div><b>Date:</b> {{ $props.date }}</div>
    <div><b>Item:</b> {{ $props.item }}</div>
    <div><b>Amount:</b> ${{$props.amount }}</div>
  </div>
</template>

<script>
export default {
  props: ['title', 'amount', 'item', 'date'],
  name: "Card"
}
</script>

<style scoped>
#card {
  border: 2px solid #598C58;
  border-radius: 10px;
  background-color: #DDE8B3;
  padding: 8px 100px 8px 100px;
  width: auto;
  height: 25%;
  margin: 3px;
}
</style>