<template>
  <!-- EXPLANATION: add on click function to close modal when clicking the backdrop -->
  <div class="backdrop" @click="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <h1 class="modal__heading">{{ header }}</h1>
      <p>{{ text }}</p>
      <p>{{ views }}</p>
    </div>
  </div>
</template>
<script>
// EXPLANATION: we want to close the modal when the backdrop is click, which is in this component. But the logic with the function toggleModal to open and close the modal is in App. We need to use a custom event. A custom event can be fired from a component and be listened to from the parent component.
// 1) We emit, we fired the custom event inside the closeModal function. this.$emit(''); emit is a function and the argument we pass in this function will be the name of the event we want to emit. This name can be anything we want as it is a custom function this.$emit('close');
// 2) In App the custom event will be listened inside the <Modal /> component use, with @close="toggleModal"
export default {
  props: ['header', 'text', 'theme'],
  methods: {
    closeModal() {
      this.$emit('close');
    },
  },
};
</script>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

.modal__heading {
  color: #03cfb4;
  border: none;
  padding: 0;
}

.modal.sale {
  background: crimson;
  color: white;
}
.modal.sale.h1 {
  color: white;
}
</style>
