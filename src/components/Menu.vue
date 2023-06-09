<template>
    <div class="menu">
        <div class="line"></div>
        <div class="hexagono">
            <img src="../assets/iconeMenu.png">
        </div>
        <div class="hexagono">
            <img src="../assets/iconeMenu.png">
        </div>
        <div class="hexagono">
            <img src="../assets/iconeMenu.png">
        </div>
    </div>
</template>

<style>
.line{
    position: absolute;
    right: 4.6rem;
    top: 5rem; 
    width: 10px;
    height: 20rem;
    background-color: #901503;
}
.menu{
    position: absolute;
    z-index: 90;
    right: 0rem;
    top: 5rem;
}
.hexagono {
    display: flex;
    background-image: url("../assets/hexagono.svg");
    background-size: 100% 100%;
    width:10rem;
    height: 10rem;
    position: relative;
    transition: ease-in 0.5s;
    justify-content: center;
    align-items: center;
 }

 .hexagono img{
    height: 50%;
    width: 50%;
 }

 .hexagono:hover{
    background-image: url("../assets/hexagono_s.svg");
 }
</style>