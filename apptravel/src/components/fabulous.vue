<template>
<div class="landingVideoContener">

    <h1 class="landingTitle">
        your<br>
        fabulous<br>
        adventure<br>
        begins now
    </h1>
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
#videoLanding{
    position: fixed;
    width:100%;
    min-height: 100vh;
    font-family: 'Poppins', sans-serif;
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
    font-size:15vmin;
    letter-spacing: 8vmin;
    text-align: center;
    font-weight: bold;
    mix-blend-mode:screen;
    text-transform: uppercase;
    text-align: left;
}

</style>