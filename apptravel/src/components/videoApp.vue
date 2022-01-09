<template>
  <div class="videoContener">
    <video
      preload="auto"
      loading="lazy"
      playsinline
      muted
      autoplay
      loop
      poster=""
      id="videoLanding"
    >
      <source src="../assets/Lake - 91562.mp4" type="video/mp4" />
    </video>
  </div>
</template>

<style>
.videoContener {
  width: 100%;
  height: 100vh;
  position: fixed;
  bottom: 0;
  left: 0;
}
#videoLanding {
  position: absolute;
  object-fit: cover;
  width: 100%;
  height: 100vh;
}
</style>
