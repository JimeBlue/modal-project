<template>
  <!-- EXPLANATION: add on click function to close modal when clicking the backdrop. IMP: we use the same click event for both modals -->
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot></slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ['theme'],
  methods: {
    //  We emit, we fired the custom even
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

.modal .actions {
  text-align: center;
  margin: 30px 0 10px 0;
}

.modal .actions a {
  color: #333;
  padding: 8px;
  border: 1px solid #eee;
  text-decoration: none;
  border-radius: 4px;
  margin: 10px;
}

.modal.sale {
  background: crimson;
  color: white;
}
.modal.sale.h1 {
  color: white;
}

.modal.sale .actions {
  color: white;
}

.modal.sale .actions a {
  color: white;
}
</style>
