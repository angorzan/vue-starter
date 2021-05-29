<template>
  <div id="app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div id="info" v-if="authenticated">
      <h1>Witaj {{ email2 }} !</h1>
      <button @click="logout()">Wyloguj</button>
    </div>
    <div id="intro" v-else>
      <div>
        Zaloguj się e-mailem
        <input type="email" v-model="email2" />
        <button @click="loginByEmail()">Wchodzę</button>
      </div>
    </div>
  </div>
</template>

<script>
import 'milligram';
export default {
  data() {
    return {
      email2: "",
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
