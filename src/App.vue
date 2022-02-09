<template>
  <h1>{{title}}</h1>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>{{title}}</h1>
      <p>{{text}}</p>
    </Modal>
  </teleport>
  <teleport to=".modals" v-if="showModal2">
    <Modal theme="sale" @close="toggleModal2">

      <h1>{{title2}}</h1>
      <p>{{text2}}</p>
    </Modal>
  </teleport>
  <button @click="toggleModal">
    open modal 1
  </button>
  <button @click="toggleModal2">
    open model 2
  </button>
</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components:{
    Modal,
  },
  data(){
    return{
      title: 'My first Vue app',
      header: "Sing up for the Giveaway",
      text: "Grab your ninja swag for half price!",
      showModal: false,
      showModal2: false,
      title2: 'Sing up to the newsletter',
      text2: 'For updates and promo codes!',
    }
  },
  methods:
      {
        toggleModal(){
          this.showModal = !this.showModal
        },
        toggleModal2(){
          this.showModal2 = !this.showModal2
        }
      }
}
</script>

<style >
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
}
button{
  background: none;
  padding: 10px 20px;
  border-radius: 10px;
  border: 1px solid black;
  margin-top: 40px;
  margin-left: 30px;
}

</style>
