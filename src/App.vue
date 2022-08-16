<template>
  <!-- EXPLANATION: CHALLENGE - CREATE ANOTHER MODAL
1)Create an extra button to open a different modal
2)Use the same modal component but pass in a different template (slot)
3)Use a different method (e.g toggleModalTwo()) and data (e.g showModalTwo)
-->
  <h1>{{ title }}</h1>
  <p>Welcome...</p>

  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag for half the price!</p>
    </Modal>
  </div>

  <!-- EXPLANATION: put the new modal in a div with the directive v-if, to only show the modal if showModalTwo is true -->
  <div v-if="showModalTwo">
    <!-- EXPLANATION: add button to open the new modal by calling the function toggleModaltwo on click-->
    <Modal @close="toggleModalTwo">
      <h1>Sign up to the newsletter</h1>
      <p>For updates and promo codes</p>
    </Modal>
  </div>

  <button @click="toggleModal">open modal</button>
  <button @click="toggleModalTwo">open modal two</button>
</template>

<script>
import Modal from './components/Modal';
export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My fist Vue app 😇 ',
      showModal: false,
      // EXPLANATION: add the property showModalTwo to dynamically output the modal (false we don´t show it, true we show it)
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    // EXPLANATION: this function reverse the the value of the variable showModalTwo
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
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
</style>
