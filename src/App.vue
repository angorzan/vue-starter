<template>
  <div id="app">
    <div id="intro">
      <h1>Witaj w systemie zapisów na zajęcia</h1>
      <div>
        Zaloguj się e-mailem <input type="email" v-model="email2" style="margin-right: 2px"/>
        <button @click="loginByEmail()">Wchodzę </button>
      </div>
    </div>
    <div id="info" style="display: none">
      <h1>Witaj {{ email2 }} !</h1>
      <button @click="quit()">Wyloguj </button>
    </div>

    <!-- <h1>Twój e-mail to {{ email }}</h1>
    <input type="email" v-model="email" />
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
    <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "anna.gorzanowska@gmail.com",
      email2: "",
      password: "",
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    loginByEmail() {
      document.querySelector("#intro").style = "display: none";
      document.querySelector("#info").style = "display: block";
    },
    quit() {
      document.querySelector("#info").style = "display: none";
      document.querySelector("#intro").style = "display: block";
    }
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
