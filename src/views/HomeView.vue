<template>
  <div class="home">
    <h1 :class="classUser">Hello {{ username }} {{ titleOfUser }} 🥉</h1>
    <img v-if="message !== undefined" alt="Vue logo" src="../assets/logo.png">
    <HelloWorld v-if="message !== undefined"
                :user-title="titleOfUser"
                :display-cli="true"
                :display-warning="true"
                :msg="message"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  data(){
    return {
      message: undefined,
      username: 'Ark',
    }
  },
  computed: {
    titleOfUser() {
      if(this.username === "Ark"){
        return 'dieu du code';
      }
      return 'sale bronze';
    },
    classUser() {
      if(this.username === "Ark"){
        return 'h1';
      }
      return 'h4';
    }
  },
  mounted(){
    setTimeout(() => {
      this.message = navigator.userAgent;
    }, 1500)
  }
}
</script>