<template>
  <div class="backdrop">
    <!-- EXPLANATION: conditionally adding the class sale, if the prop theme equals sale -->
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <h1 class="modal__heading">{{ header }}</h1>
      <p>{{ text }}</p>
      <p>{{ views }}</p>
    </div>
  </div>
</template>
<script>
// EXPLANATION:  To use the props passed from App:
// 1) Tell Vue that this component should accept a certain prop. I do that by creating a component object with a property called props, which will have an array as a value with the names of all the props this component will be accepting
// Use the prop inside the template. In this case, I´m using it inside the <h1>

export default {
  props: ['header', 'text', 'theme'],
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
