<template>
  <header>
    <div id="title">
      <img
          id="money-with-wings"
          src="../assets/images/money-with-wings-emoji.png"
          alt="Money with Wings Logo"
      >
    </div>
    <div class="text"><b>Money &dollar;aver</b></div>
  </header>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>
#title{
  margin: 5px;
  font-size: 20px;
  text-align: center;
}

#money-with-wings{
  height: 80px;
  width: 115px;
}

.text{
  font-size: 35px;
}

</style>