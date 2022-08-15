<template>
<h1>{{title}}</h1>
</template>

<script>
// object representing the root component
export default {
  name: 'App',
 data() {
  return {
    title: "My fist Vue app 😇 "
  }
 }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border: 3px solid blue
}
</style>
