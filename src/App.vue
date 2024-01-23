<template>
  <h1>{{ title }}</h1>
  <teleport to="#modal">
    <div v-if="showModal">
      <Modal header="Sign ups!" :data="arrayObject" theme="sale" @close="closeModalFunction">
        <template v-slot:links>
          <a href="#">signup now</a>
          <a href="#">/moreinfo now</a>
          <button @click="showModalFunction2">Show Modal</button>
        </template>

      </Modal>
    </div>
    <div v-if="showModalTwo">
      <Modal header="Modal Two!" :data="arrayObject" theme="dark" @close="closeModalFunction2">
      </Modal>
    </div>
  </teleport>

    <button @click="showModalFunction">Show Modal</button>
    <button @click="showModalFunction2">Show Modal 2</button>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
  name: 'App',
  components: {
    Modal
    // HelloWorld
  },

  data() {
    return {
      title: 'My first vue program',
      arrayObject: {
        name: "John Rey Decosta",
        age: 16,
        address: "Polomolok South Cotabato"
      },
      showModal: false,
      showModalTwo: false

    }
  },
  methods: {
    showModalFunction() {
      this.showModal = !this.showModal;
    },
    closeModalFunction(val) {
      this.showModal = val;
      alert(val);
    },
    showModalFunction2() {
      this.showModalTwo = !this.showModalTwo;
    },
    closeModalFunction2(val) {
      this.showModalTwo = val;

    }

  }
}
</script>

