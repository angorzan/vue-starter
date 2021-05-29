<template>
  <div id="app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div id="info" v-if="authenticated">
      <h3>Zalogowany jako {{ email }} !</h3>
      <button @click="logout()">Wyloguj</button>
    </div>
    <div id="intro" v-else>
      <login-form @login="logIn($event)"></login-form>
    </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
export default {
  components: { LoginForm },
  data() {
    return {
      email: "",
      authenticated: false,
    };
  },
  methods: {
    loginByEmail() {
      this.authenticated = true;
    },
    logout() {
      this.authenticated = false;
    },
    logIn(username) {
      this.authenticated = true;
      this.email = username;
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
</style>
