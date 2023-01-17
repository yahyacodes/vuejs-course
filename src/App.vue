<template>
  <h1>{{ title }}</h1>
  <p>Welcome....</p>
  <Teleport to=".modals" v-if="showModal">
    <ModalVue theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">more ifo</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag for half price</p>
    </ModalVue>
  </Teleport>

  <Teleport to=".modals" v-if="showModalTwo">
    <ModalVue @close="toggleModalTwo">
      <h1>This is the second modal</h1>
      <p>This is modal two practice in vuejs</p>
    </ModalVue>
  </Teleport>

  <button @click="toggleModal">open modal</button>
  <button @click="toggleModalTwo">open modal two</button>
</template>

<script>
// Challange One
// - create an extra button to open different modal
// - use the same modal componet but pass different template (slot)
// - use a different method (eg toggleModalTwo) and data (eg showModalTwo)

import { Teleport } from "vue";
import ModalVue from "./components/ModalVue.vue";

export default {
  name: "App",
  components: {
    ModalVue,
    Teleport,
  },
  data() {
    return {
      title: "My first vue App",
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
#app,
.modals {
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
