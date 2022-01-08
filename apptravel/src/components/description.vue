<template>

<div class="description">
<div class="articleDescription">
<div class="descriptioParah">
<h1>Préparez votre <br> voyage</h1>
<div class="trait"></div>
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Incidunt, deserunt inventore. Voluptate expedita nulla, accusamus non impedit dolore animi neque recusandae labore numquam vitae quo magnam debitis sed, ipsum nam.</p>
</div>
<img src="../assets/philipp-kammerer-6Mxb_mZ_Q8E-unsplash.jpg" alt="">
</div>
</div>

</template>
    
<script setup>


</script>

<style scoped>
.description{
    width: 100%;
    min-height: 100vh;
    position: relative;
    background-color: white;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    z-index: 5;
}
.articleDescription{
width: 80vw;
min-height: 70vh;
display: flex;
flex-direction: row;
align-items: flex-start;
justify-content: space-evenly;
}
.descriptioParah{
flex: 0.3;
}.descriptioParah h1{
        font-family: 'Poppins', sans-serif;
        font-size: 3rem;
        margin-top: 0;   
        color: black;
        line-height: 4rem;
}
.trait{
    background-color:#c0392b;
    width: 50%;
    height: 2px;
    z-index: 1;
    margin-bottom: 10vh;
}
.descriptioParah p{
    width: 70%;
    font-family: 'Roboto', sans-serif;
    font-weight: bold;
    font-size: 1.1rem;
}
img{
flex: 0.5;
height: auto;
max-width: 50%;

}

</style>