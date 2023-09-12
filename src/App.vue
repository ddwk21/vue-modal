<template>
  <h1>{{ title }}</h1>
  <p>Welcome!</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links >
        <a href="#">Sign Up Now!</a>
        <br>
        <a href="#">More Info</a>
      </template>
      <h1>Welcome to our Giveaway!</h1>
      <p>Win a new BMW M2</p>

    </Modal>
  </teleport>
  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sorry!</h1>
      <p>There is no giveaway at this time, try again later.</p>
    </Modal>
  </div>

  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModalTwo">Open other Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App :D',
      header:"Sign up for the Giveaway",
      text:"Win a new BMW M2",
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
    }
  }
}
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
