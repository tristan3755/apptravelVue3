<template>
  <div class="sectForm" @keyup.enter="fetchApi">
  <div class="dashboard">
  <input type="text" placeholder="Inscrivez le pays de votre destination" v-model="nomPays"/>
    <button @click="fetchApi">Rechercher</button>
  </div>
  <div class="container-intel">
      <div class="divIntel flag">
      <img :src=flag>
      </div>
      <div class="divIntel border">
      <p>Borders :</p>
     <p v-for="border in countryBorders">{{ border }}</p>
      </div>
       <div class="divIntel border">
      <p>Name :</p>
        <p v-for="namesSpelling in names">{{ namesSpelling }}</p>
      </div>
        <div class="divIntel border">
      <p>Name :</p>
        <p v-for="namesSpelling in names">{{ namesSpelling }}</p>
      </div>
      <p v-for="capitalsName in capitals">{{ capitalsName }}</p>
      <p>{{ regionName }}</p>
      <p>{{ population }}</p>
      <p>{{ languagesCountry }}</p>
      </div>
    </div>
</template>

<script setup>
import { ref } from "vue";

let nomPays = ref("");
let countryBorders = ref("");
let names=ref("")
let capitals=ref("")
let regionName=ref("")
let population=ref("")
let flag=ref("")
let languagesCountry=ref("")
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
    names.value = res[0].altSpellings;
    capitals.value = res[0].capital;
    regionName.value = res[0].region;
    population.value=res[0].population;
    flag.value=res[0].flags['png'];
    languagesCountry.value=res[0].languages;
    console.log(languagesCountry.value);
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
  height: auto;
  background-color: white;
  display: flex;
  flex-direction: column;
}
.dashboard{
  height: 250px;
  width: 100%;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-evenly;
}
.dashboard input{
border-radius: 50px;
width:30vw;
height: 100px;
background: #ffffff;
box-shadow:  5px 5px 10px #d9d9d9,
             -5px -5px 10px #ffffff;
  border: none;
  text-align: center;
    color: black;
  font-family: "Roboto", sans-serif;
  font-weight: bold;
  font-size: 1.5rem;
}
button {
  border-radius: 50px;
background: #ffffff;
box-shadow:  5px 5px 10px #d9d9d9,
             -5px -5px 10px #ffffff;
  border: none;
  padding: 1.5rem;
  color: black;
  font-family: "Roboto", sans-serif;
  font-weight: bold;
  font-size: 1.1rem;
  letter-spacing: 1.5px;
}
.container-intel{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  min-height: auto;
  width: 90vw;
  align-self: center;
  justify-content:space-evenly;
}
.divIntel{
      border-radius: 5px;
background: #ffffff;
box-shadow:  5px 5px 10px #d9d9d9,
             -5px -5px 10px #ffffff;
             min-height: 200px;
             min-width: 300px;
             position: relative;  
             margin: 5rem;         
}
.flag{
  height: 200px;
}
.flag img{
  position: absolute;
  object-fit: cover;
  width: 100%;
  height: 100%;
  border-radius: 5px;
}
.border{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
.border>*{
  margin: 1rem;
}
</style>
