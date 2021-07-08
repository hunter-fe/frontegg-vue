<template>
  <div id="app" v-if="fronteggLoaded">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <p>
      Logged in as
      {{ this.authState.user ? this.authState.user.email : "Not logged in" }}
    </p>
    <button v-on:click="showAdminPortal">Open admin portal</button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import { openAdminPortal } from "@frontegg/vue";

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      ...this.mapAuthState(),
    };
  },
  methods: {
    showAdminPortal() {
      openAdminPortal();
    },
  },
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
