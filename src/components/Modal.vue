<template>
  <!-- EXPLANATION: THE PROBLEM. We want to the modal to be closed when the user clicks on the backdrop itself, the  not when the user the clicks on other element inside the backdrop, like the modal. But the other elements inside the backdrop are children of the backdrop and therefore part of it. So, we want to restrict the click event to just the backdrop element and not when the user clicks on the modal inside it-->
  <!-- EXPLANATION: THE SOLUTION: use a click event modifier, which will modify how the click event is register and when we react to it -->
  <!-- EXPLANATION: THE IMPLEMENTATION: I added the self modifier to the click event below, so that the click event will only have effect if the user clicks on the backdrop and not somewhere else-->
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <h1 class="modal__heading">{{ header }}</h1>
      <p>{{ text }}</p>
      <p>{{ views }}</p>
    </div>
  </div>
</template>
<script>
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
