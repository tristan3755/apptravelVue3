<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import videoApp from './components/videoApp.vue'
import landingPage from './components/landingPage.vue'
import description from './components/description.vue'
import fabulous from './components/fabulous.vue'
import transparence from './components/transparence.vue'
import formApp from './components/formApp.vue'
</script>

<template>
<article>
<videoApp/>
<landingPage/>
<description/>
<fabulous/>
<transparence/>
<formApp/>
</article>
</template>

<style>
body{
  margin: 0;
  padding: 0;
}
*{
  box-sizing: border-box;
  scroll-behavior: smooth;
}
#app {
width: 100%;
min-height: 100vh;
}


</style>
