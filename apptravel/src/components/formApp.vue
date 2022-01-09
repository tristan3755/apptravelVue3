<template>
  <div class="sectForm">
    <div class="app">
      <input
        type="text"
        placeholder="Inscrivez le pays de votre destination"
        v-model="nomPays"
      />

      <p v-for="border in countryBorders">{{ border }}</p>

      <textarea> </textarea>
      <button @click="fetchApi">Rechercher</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

let nomPays = ref("");
let countryBorders = ref("");
let urlApi = "https://restcountries.com/v3.1/name/";
function fetchApi() {
  fetch(urlApi + "{" + nomPays.value + "}", {
    methods: "GET",
    headers: {
      "Content-Type": "application/json; charset=UTF-8",
    },
  })
    .then((res) => res.json())
    .then((res) => {
      console.log(res);
      countryBorders.value = res[0].borders;
      console.log(countryBorders);
    })
    .catch((error) => {
      console.log(error);
    });
}
</script>

<style scoped>
.sectForm {
  position: relative;
  width: 100%;
  min-height: 100vh;
  background-color: white;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}
.app {
  min-height: 80vh;
  flex: 0.8;
  background: #ffffff;
  box-shadow: inset 5px 5px 10px #e0e0e0, inset -5px -5px 10px #ffffff;
  border-radius: 5px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
}
button {
  border-radius: 5px;
  background: linear-gradient(145deg, #e6e6e6, #ffffff);
  box-shadow: 5px 5px 10px #e0e0e0, -5px -5px 10px #ffffff;

  border: none;
  padding: 1.5rem;
  color: black;
  font-family: "Roboto", sans-serif;
  font-weight: bold;
  font-size: 1.1rem;
  letter-spacing: 1.5px;
}
.app textarea {
  border-radius: 15px;
  resize: none;
  width: 50%;
  flex: 0.7;
  border: none;
  background: linear-gradient(145deg, #e6e6e6, #ffffff);
  box-shadow: 5px 5px 10px #e0e0e0, -5px -5px 10px #ffffff;
}
.app input {
  width: 30%;
  flex: 0.1;
  font-family: "Roboto", sans-serif;
  font-weight: bold;
  font-size: 1.1rem;
  background: linear-gradient(145deg, #e6e6e6, #ffffff);
  box-shadow: 5px 5px 10px #e0e0e0, -5px -5px 10px #ffffff;

  border: none;
  border-radius: 5px;
}
</style>
