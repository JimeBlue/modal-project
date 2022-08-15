

<template>
<!-- EXPLANATION: TEMPLATE REFS are used to grab dom elements like we did querySelector in vanilla JS -->
<h1>{{title}}</h1>
<!-- EXAMPLE: -->
<!-- EXPLANATION: give the input element a ref with a name -->
<input type="text" ref="name">
<!-- EXPLANATION: add on click event to the button and call the handleClick function -->
<button @click="handleClick">Click me</button>
</template>

<script>
// object representing the root component
export default {
  name: 'App',
 data() {
  return {
    title: "My fist Vue app 😇 "
  }
 },
 methods: {
handleClick () {
  // EXPLANATION: when btn is clicked console log the element with the ref name
  console.log(this.$refs.name)
    // EXPLANATION: when btn is clicked add the class active to the element with the ref name
  this.$refs.name.classList.add("active")      
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
