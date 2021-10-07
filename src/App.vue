<template>
  <div id="app">
    <Cadastro />
  </div>
</template>

<script>
import Cadastro from "@/components/Cadastro.vue";
export default {
  name: "App",
  components: {
    Cadastro,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@500&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Comfortaa:wght@700&display=swap");

body {
  background-color: var(--cta-1);
}
#app {
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 25px;
}
.btn-primary,
.btn-primary:hover,
.btn-primary:focus {
  font-family: "Comfortaa", sans-serif;
  background-color: var(--primary-0);
  color: var(--secondary-0);
  text-transform: uppercase;
  box-shadow: none;
}
.btn-secondary,
.btn-secondary:hover,
.btn-secondary:focus {
  font-family: "Comfortaa", sans-serif;
  background-color: var(--cta-0);
  color: var(--secondary-7);
  text-transform: uppercase;
  border: none;
}
.bg-primary {
  background-color: var(--primary-0) !important;
}
h1{
  font-size: 2.20rem;
}
h1,
.text-primary {
  font-family: "Comfortaa", sans-serif;
  color: var(--primary-0) !important;
  text-decoration: none;
}
.form-control,
.form-select {
  border: 1px solid var(--primary-0);
}

input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
}


</style>
