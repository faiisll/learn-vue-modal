<template>
  <h1>{{ title }}</h1>
  <input ref="name" type="text" />
  <button @click="toggleModal">Toggle Modal</button>
  <div v-if="showModal">
    <Modal theme="danger" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Submit</a>
        <a href="#">Close</a>
      </template>
      <h1>Ninja</h1>
      <p>Ninja paragraph</p>
    </Modal>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My First Vue via CLI",
      header: "header by props",
      showModal: false,
    };
  },
  methods: {
    handleClick() {
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
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
