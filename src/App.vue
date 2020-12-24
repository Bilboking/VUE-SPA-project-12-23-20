<template>
  <h1>{{ title }}</h1><br>
    <div v-if="showModal">
       <Modal theme="sale" @close="toggleModal">
        <template v-slot:links>
          <a href="#">Sign up now!</a>
          <a href="#">more info</a>
        </template>
          <h1>Sign up for Bruce's newsletter!</h1>
          <p>Get incredible information delivered to your inbox!</p>
        </Modal>
    </div>
    <button @click.alt="toggleModal">open modal (alt)</button>
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
      header: "Sign up for Bruce's newsletter!",
      text: "Get incredible information delivered to your inbox!",
      showModal: false
    }
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
