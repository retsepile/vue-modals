<template>
  <h1>{{ title }}</h1>
  <p>Welcome....</p>
  <teleport to="#modals" v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign Up NOW!</a>
        <a href="#">More INFO</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag for half the Price!</p>
    </Modal>
  </teleport>

  <teleport to="#modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign Up to the Newsletter</h1>
      <p>For updates and promo codes!!!!</p>
    </Modal>
  <!-- <input type="text" ref="name">
  <button @click="handleClick">Click Me</button> -->
  </teleport>
  <button @click.left="toggleModal">Open Modal (left)</button> 
   <button @click="toggleModalTwo">Open Modal </button> 
</template>

<script>
// challenge
// -create an extra button to oprn a dfferent modal
// -use the same modal component but pass in a different template(slot)
// -use a diferent method(e.g. toggleModalTwo) and data (e.g. showModalTwo)

import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data(){
    return{
      title: 'My First Vue App :)',
      showModal:false,
      showModalTwo:false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    },
  }
  // methods: {
  //   // handleClick() {
  //   //   console.log(this.$refs.name)
  //   //   this.$refs.name.classList.add('active')
  //   //   this.$refs.name.focus()
  //   // }
  // }

}
</script>

<style>
#app , #modals{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
