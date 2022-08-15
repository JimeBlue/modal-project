<template>
  <h1>{{ title }}</h1>
  <!-- EXPLANATION: add an attribute to a component to pass props, in this case I add the attribute header and I pass a string to the component. EXAMPLE:       header="Sign up for the giveaway!"
    text="Grab your ninja swag for half price" 
    IMP: the name of the attribute can be anything I want -->
  <!-- EXPLANATION: if I want to pass a value other than a string as prop or a string that it is inside a variable in the data object of App, I need to add a data bind to the component. I do that using a semicolon before the attribute name. In this case :header="header". IMP: this is the most common way of passing props -->
  <!-- EXPLANATION: if I want conditionally add specific styles, I can pass property, in this case theme="sale". This explanation continues in Module -->
  <Modal :header="header" :text="text" theme="sale" />
</template>

<script>
import Modal from './components/Modal';
export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My fist Vue app 😇 ',
      header: 'Sign up for the giveaway!',
      text: 'Grab your ninja swag for half price',
      views: '1000 views',
    };
  },
};
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
h1 {
  border: 3px solid blue;
}
</style>
