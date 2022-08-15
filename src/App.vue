

<template>
  <!-- note: multiple components branch 23 -->

  <h1>{{ title }}</h1>
  <Modal />
</template>

<script>
// EXPLANATION: how to use the Modal component inside App component:
// 1) Import the modal component
// 2) Register that we want to use Modal inside App by creating a components property with an object as a value, and adding the component inside the object
// 3) Use it inside the template

import Modal from './components/Modal.vue';
export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My fist Vue app 😇 ',
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
