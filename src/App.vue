<template>
  <h1>{{ title }}</h1><br>
    <teleport to="#modals" v-if="showModal">
       <Modal theme="sale" @close="toggleModal">
        <template v-slot:links>
          <a href="#">Sign up now!</a>
          <a href="#">more info</a>
        </template>
          <h1>Sign up for Bruce's newsletter!</h1>
          <p>Get incredible information delivered to your inbox!</p>
        </Modal>
    </teleport>

    <teleport to="#modals" v-if="showModalTwo">
       <Modal @close="toggleModalTwo">
          <h1>Today's News</h1>
          <p>All the latest information!</p>
        </Modal>
    </teleport>
    <button @click="toggleModal">open modal one</button>
    <button @click="toggleModalTwo">open modal two</button>
 <!-- <input type="text" ref="name" >
  <button @click="handleClick">click me</button>-->
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data(){
    return {
      title: 'My First Vue App :)',
      showModal: false,
      showModalTwo: false
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
#app, #modals {
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
