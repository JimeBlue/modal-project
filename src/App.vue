<template>
  <!-- EXPLANATION: SLOTS: alernative to props to pass more complex information, i.e templates to reusable components. The implementation is as follow
  1) We can´t use a self closing component tag, we need to open and close it
  2) Inside <Modal> </Modal> pass a template. This template is know as slot
  3) Use the slot inside Modal.vue
  -->
  <!-- EXPLANATION: we can also pass name slots, which will have a specific structure. I.e, If I want a slot to have something different inside from the others, I will use a name slot inside of it. To use them:
  1) I use the template tag when I want to pass them
  2)Put inside the template tag whatever html I want to pass
  3) Give the template a name, using the slot directive (<template v-slot:links>)
  4) Output the name slot in Modal.vue
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

  <button @click="toggleModal">open modal</button>
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
      showModal: false,
    };
  },
  methods: {
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
</style>
