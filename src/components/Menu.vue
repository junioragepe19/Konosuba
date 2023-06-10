<script>
export default {
  methods: {
    gotoComponent(value) {
        console.log(value)
        this.$scrollTo(value);
    }
  }
}
</script>

<template>
  <div class="menu">
    <div class="line"></div>
    <div class="hexagono" @click="gotoComponent('#Home')">
      <figure class="figura">
        <img src="../assets/iconeMenu.png">
        <figcaption>Home</figcaption>
      </figure>
    </div>
    <div class="hexagono" @click="gotoComponent('#About')">
      <figure class="figura">
        <img src="../assets/iconeMenu.png">
        <figcaption>Story</figcaption>
      </figure>
    </div>
    <div class="hexagono" @click="gotoComponent('#Characters')">
      <figure ref="aboutRef" class="figura" >
        <img src="../assets/iconeMenu.png">
        <figcaption>Characters</figcaption>
      </figure>
    </div>
  </div>
</template>

<style>
@import url('../app.scss');

.figura{
    position: absolute;
    margin: auto;
    width: 100%;
}
.line{
    position: absolute;
    right: 4.6rem;
    top: 5rem; 
    width: 10px;
    height: 20rem;
    background-color: #901503;
}
.menu{
    position: fixed;
    z-index: 250;
    right: 0rem;
    top: 5rem;
}
.hexagono {
    cursor: pointer;
    font-family: 'Konosuba';
    color: white;
    display: flex;
    text-align: center;
    background-image: url("../assets/hexagono.svg");
    background-size: 100% 100%;
    width:10rem;
    height: 10rem;
    position: relative;
    transition: ease-in 0.1s;
    justify-content: center;
    align-items: center;
 }

 .hexagono img{
    width: 50%;
 }
 
 .hexagono:hover{
    background-image: url("../assets/hexagono_s.svg");
 }
</style>