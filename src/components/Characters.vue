<script>
import { ref } from 'vue';
export default {

    name: 'App',
    setup() {
        var characterSelected = ref(null);
        const urlCharacters = [{url_code: "/src/assets/KazumaFull.png", name_char: "Satou Kazuma", age: "17", desc:
        "Ele é conhecido por sua personalidade preguiçosa, egocêntrica e até mesmo trapaceira, mas também tem um bom coração. Apesar de inicialmente se ressentir de ser enviado para outro mundo,\
        ele logo se adapta à situação e decide se tornar um aventureiro para ganhar dinheiro e sobreviver."},
        {url_code: "/src/assets/MeguminFull.png", name_char: "Megumin", age: "14"},
        {url_code: "/src/assets/DarknessFull.png", name_char: 'Dustiness Ford Lalatina "Darkness"', age: "19"},
        {url_code: "/src/assets/AquaFull.png", name_char: 'Aqua', age: "∞"}]

        function selectCharacter(index){
            characterSelected.value = index;
        }
        function verifyNumber(num){
            return characterSelected.value == num
        }
        return {
            urlCharacters, characterSelected, selectCharacter, verifyNumber
        };
    }
}
</script>

<template>
    <h1 class="title">
        <span class="first">Per</span>
        <span class="second">so</span>
        <span class="third">na</span>
        <span class="first">gens</span></h1>
    <div class="main-content">
        <div class="character-selected-container">
            
            <img class="character-selected" :src="characterSelected !== null ? urlCharacters[characterSelected].url_code : ''">
       
        </div>
        <div v-if="characterSelected != null" class="text-character">
            <div class="text">
                Nome: {{ urlCharacters[characterSelected].name_char }}
                
            </div>
            <div class="text">
                Idade: {{ urlCharacters[characterSelected].age }} anos
            </div>
            <div class="text">
                {{ urlCharacters[characterSelected].desc }}
            </div>
        </div>
        <div class="list-characters">
            <div class="character" @click="selectCharacter(0)">
                <img :class="{'grayscale' : !verifyNumber(0)}" src="../assets/KazumaIcon.png">
            </div>
            <div class="character" @click="selectCharacter(1)" >
                <img :class="{'grayscale' : !verifyNumber(1)}" src="../assets/MeguminIcon.png"> 
            </div>
            <div class="character" @click="selectCharacter(2)">
                <img :class="{'grayscale' : !verifyNumber(2)}" src="../assets/DarknessIcon2.png">
            </div>
            <div class="character" @click="selectCharacter(3)">
                <img :class="{'grayscale' : !verifyNumber(3)}" src="../assets/AquaIcon.png">
            </div>
        </div>
        
    </div>
</template>

<style>
    @import '../app.scss';
    .text{
        color: #4c3728;
        margin-left: 2rem;
        margin-top: 2rem;
        margin-right: 2rem;
    }
    .text-character{
        font-family: 'Konosuba';
        position: absolute;
        top:10rem;
        right: 2rem;
        width: 35%;
        height: 50%;
        background-image: url("../assets/backgroundText.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
        transition: ease-in s;    
    }
    .normalscale{
        filter: grayscale(0) !important;
    }
    .grayscale{
        filter: grayscale(1);
        transition: ease-in 0.1s ;
    }
    .grayscale:hover{
        filter: grayscale(0) !important;
    }
    .title{
        text-align: center;
        font-family: 'Konosuba';
        font-size: 4rem;
    }
    .main-content{
        position: relative;
        width: 100%;
        height: 50rem;
        background-image: url("../assets/backgroundCharacters.png");
        justify-content:center;
        display: flex;
        align-items: center;

    }
    .character-selected-container{
        z-index: 99;
        width: 60%;
        height: 10%;
        position: absolute;
        top: 9rem;
        left: 0rem;
    }
    .character-selected{
        position: relative;
        padding-top: 2rem;
        width: 86%;
    }
    .list-characters{
        z-index: 100;
        position: absolute;
        bottom: 0;
        display: flex;
        flex-direction: row;
        
    }
    .character{
        cursor: pointer;
        display: flex;
        position: relative;
        width: 12rem;
        height: 12rem;
        border-color: darkgoldenrod !important;
        border-width: 2px !important;
        border-style: solid;
        background-color: #1E1D21;
        margin-left: 0.5rem;
        transition: ease-in-out 0.1s;
    }
    .character img{
        max-width: 100%;
        max-height: 100%;
    }
    .first{
        color: #FF00A2;
    }
    .second{
        color: #FFC948;
    }
    .third{
        color: #901503;
    }
</style>