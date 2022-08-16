<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <!-- EXPLANATION: put the modal in a div with the directive v-if, to only show the modal if showModal is true -->
  <div v-if="showModal">
    <!-- EXPLANATION:  @close="toggleModal" is the custom event that listents the call from the Modal.vue component. Wheneven this call is listened the toggleModal function run, closing the modal-->
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
  </div>
  <!-- EXPLANATION: add button to open the modal by calling the function toggleModal on click-->
  <button @click="toggleModal">open modal</button>
</template>

<script>
// EXPLANATION: add the property showModal to dynamically output the modal (false we don´t show it, true we show it)
import Modal from './components/Modal';
export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My fist Vue app 😇 ',
      header: 'Sign up for the giveaway!',
      text: 'Grab your ninja swag for half price',
      showModal: false,
    };
  },
  methods: {
    // EXPLANATION: this function reverse the the value of the variable showModal
    toggleModal() {
      this.showModal = !this.showModal;
    },
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
