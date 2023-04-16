<template>
  <router-link class="link" to="/">Home</router-link> |
  <router-link class="link" to="/about">About</router-link> |
  <router-link class="link" to="/payments">Payments</router-link>
</template>

<script>

export default {
  name: "NavBar",

  setup() {

  }
}
</script>

<style scoped>
.link{
  font-size: 15px;
}
</style>