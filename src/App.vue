<template>
  <h1>{{ title }}</h1>
  <p>Welcome....</p>
  <div v-if="showModal">
    <ModalVue theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">more ifo</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag for half price</p>
    </ModalVue>
  </div>
  <button @click="toggleModal">open modal</button>
</template>

<script>
import ModalVue from "./components/ModalVue.vue";

export default {
  name: "App",
  components: {
    ModalVue,
  },
  data() {
    return {
      title: "My first vue App",
      header: "Sign up for the Giveaway!!",
      text: "Grab your ninja swag for half price",
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

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
