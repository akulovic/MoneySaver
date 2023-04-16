<template>
  <div id="nav">
    <Header></Header>
    <NavBar></NavBar>
  </div>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 5px 30px 30px 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #63734A;
}
</style>
<script>
import NavBar from "@/components/NavBar";
import Header from "@/components/Header";
export default {
  components: {Header, NavBar}
}
</script>