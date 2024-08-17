<template>
  <h3>{{ title }}</h3>

  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal">
      <h1>This is Modal Title</h1>
      <p>This is modal content</p>
      <template v-slot:links>
        <a href="#">Sign Up For now</a>
      </template>
    </Modal>
  </div>
  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign Up Newsletter</h1>
      <p>Get update of promo code</p>
    </Modal>
  </div>

  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModalTwo">Open Modal Two</button>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "This is my first vue app :)",
      header: "This is Modal Title",
      text: "This is modal content",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
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
