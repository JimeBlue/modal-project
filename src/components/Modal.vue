<template>
  <div class="backdrop">
    <div class="modal">
      <h1 class="modal__heading">Modal Title</h1>
      <p>modal content</p>
    </div>
  </div>
</template>

<style scoped>
/* EXPLANATION: by default the styles affect all the elements throught the App. So, if I style an <h1> here, the same style will be applied to an <h1> in App. In oder for the styles to be applied only inside a component there are two options

1) I can add the attribute scoped to <style>. This has the disadvantage that it affects performance, since Vue gives the style and the element a data number. Explanation: https://www.youtube.com/watch?v=KM1U6DqZf8M&list=PL4cUxeGkcC9hYYGbV60Vq3IXYNfDk8At1&index=5

2) I can make the style selector more specific, e.g using BEM classes

*/

/* EXPLANATION: If I have global styles, I can put them inside the folder assets, in the a folder global.css. In order to use the global styles I need to import global.css in main.js*/

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
/* EXAMPLE: 1) */
h1 {
  color: #03cfb4;
  border: none;
  padding: 0;
}
/* EXAMPLE: 2) */
.modal__heading {
  color: blue;
}
</style>
