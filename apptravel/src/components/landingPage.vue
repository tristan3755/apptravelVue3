<template>

<div class="landingVideoContener">

    <h1 class="landingTitle">
        TRAVEL<br>
        <p>Organise your trip | feel free</p>
    </h1>
    <div class="ancre" @click="scroll"><svg width="50%" height="50%" viewBox="0 0 195 255" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M191 155L97.5001 249L3.99999 155" stroke="black" stroke-width="8" stroke-linecap="round"/>
<path d="M97 238L97 8" stroke="black" stroke-width="15" stroke-linecap="round"/>
</svg>
</div>
</div>
</template>
    
<script setup>

function scroll(){
let valeur=document.querySelector('.landingVideoContener')
let valeurScroll=valeur.clientHeight
window.scrollTo(0,valeurScroll)

}
</script>

<style scoped>

.landingVideoContener{
    width: 100%;
    min-height: 100vh;
    position: relative;
}

.landingTitle{
    background-color: white;
    position: absolute;
    width: 100%;
    height: 100vh;
    position: absolute;
    font-family: 'Poppins', sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-top: 0;
    font-size:20vmin;
    letter-spacing: 8vmin;
    text-align: center;
    font-weight: bold;
    mix-blend-mode:screen;
}
.landingTitle p{
     font-size:4vmin;
    letter-spacing: 2.3vmin;
    margin-top:0;
    text-transform: uppercase;
}
.ancre{
 position: absolute;
bottom:5vh;
left: 50vw;
transform: translateX(-50%);
 border-radius: 50%;
background: #ffffff;
box-shadow:  5px 5px 10px #d9d9d9,
             -5px -5px 10px #ffffff;
width: 60px;
height: 60px;    
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
transition: ease-in-out 0.5s;
     
}
.ancre:hover{
    cursor: pointer;
      border-radius: 15px;
        background: linear-gradient(145deg, #e6e6e6, #ffffff);
        box-shadow:  31px 31px 62px #e3e3e3,
                    -31px -31px 62px #ffffff;
}
</style>