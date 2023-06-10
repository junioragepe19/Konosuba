<script setup>
</script>

<template>
  <div class="home">
    <div class="video-opacity">
      <video class="video" loop muted autoplay>
        <source src="../assets/Konosuba-Trailer.mp4" type="video/mp4">
      </video>
    </div>
    <img class="logo" src="../assets/KonosubaLogo.png"/>
    
</div>
</template>


<style>
.video{
  height: 100%;
}
.home{
  display: flex;
  align-items: center;
  justify-content: center;
}
.logo{
  width: 80%;
  display: flex;
  margin: auto;
  position: absolute;
  animation: logo_anim 2s ease-in ;
  filter: brightness(150%);
}
@keyframes logo_anim {
  from {opacity: 0;
    filter: brightness(100%);}
  to {opacity: 1;
    filter: brightness(125%);}
}
.video-opacity{
  filter: brightness(20%)
}
</style>
