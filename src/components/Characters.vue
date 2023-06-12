<script>
import { ref } from 'vue';
export default {

    name: 'Characters',
    setup() {
        var characterSelected = ref(null);
        const urlCharacters = [{url_code: "/src/assets/KazumaFull.png", name_char: "Satou Kazuma", age: "17", desc:
        "Ele é conhecido por sua personalidade preguiçosa, egocêntrica e até mesmo trapaceira, mas também tem um bom coração. Apesar de inicialmente se ressentir de ser enviado para outro mundo,\
        ele logo se adapta à situação e decide se tornar um aventureiro para ganhar dinheiro e sobreviver."},
        {url_code: "/src/assets/MeguminFull.png", name_char: "Megumin", age: "14",desc:
        "Apesar de sua fixação por explosões, Megumin é uma personagem carismática e adorável. Ela é leal aos seus amigos e está sempre pronta para protegê-los, mesmo que isso signifique usar toda\
        a sua energia em um único ataque explosivo. Sua paixão pela magia explosiva é uma característica marcante e uma das principais fontes de comédia na série. Megumin também tem um relacionamento\
        próximo com Yunyun, outra maga especializada em magia explosiva. As duas têm uma rivalidade amigável e frequentemente competem entre si."},
        {url_code: "/src/assets/DarknessFull.png", name_char: 'Dustiness Ford Lalatina "Darkness"', age: "19", desc:
        "Darkness é uma guerreira nobre e uma masoquista auto-proclamada. Ela é uma personagem extremamente peculiar, pois é obcecada por ser dominada e receber punições físicas durante as batalhas.\
        Ela anseia por combates intensos e situações de perigo, buscando a sensação de dor e submissão. Apesar de suas inclinações masoquistas, Darkness é uma personagem leal e dedicada aos seus amigos.\
        Ela está disposta a arriscar sua própria vida para protegê-los e é conhecida por sua forte determinação em batalha."},
        {url_code: "/src/assets/AquaFull.png", name_char: 'Aqua', age: "∞", desc:
        "A personalidade de Aqua é bastante infantil e imatura. Ela muitas vezes age de forma egoísta e irresponsável, causando problemas para os outros personagens. Ela também é propensa a entrar em discussões bobas e ser facilmente provocada por insultos.\
        Apesar de suas falhas, Aqua é um membro valioso do grupo principal de protagonistas, que inclui Kazuma, Megumin e Darkness. Eles formam um time disfuncional, mas divertido, em suas aventuras no Mundo de KonoSuba. Aqua traz um elemento cômico para a história\
        com suas trapalhadas e sua interação com os outros personagens."}]

        function resetScroll(){
            var elementToScroll = document.getElementById("scroll")
            elementToScroll.scrollTo(0,0)
        }
        function selectCharacter(index){
            characterSelected.value = index;
        }
        function verifyNumber(num){
            return characterSelected.value == num
        }
        return {
            urlCharacters, characterSelected, selectCharacter, verifyNumber, resetScroll
        };
    }
}
</script>

<template>
    <div class="characters">
        <h1 class="title">
            <img class="anim_title" src="../assets/KonosubaGif.gif">
            <div class="text_title">
                <span class="first">Per</span>
                <span class="second">so</span>
                <span class="third">na</span>
                <span class="first">gens</span>
            </div>
        </h1>
        <div class="main-content">
            <div class="character-selected-container">
                
                <img class="character-selected" :src="characterSelected !== null ? urlCharacters[characterSelected].url_code : ''">
        
            </div>
            <div v-if="characterSelected != null" id="scroll" class="text-character">
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
                <div class="character" @click="selectCharacter(0);resetScroll()">
                    <img :class="{'grayscale' : !verifyNumber(0)}" src="../assets/KazumaIcon.png">
                </div>
                <div class="character" @click="selectCharacter(1);resetScroll()" >
                    <img :class="{'grayscale' : !verifyNumber(1)}" src="../assets/MeguminIcon.png"> 
                </div>
                <div class="character" @click="selectCharacter(2);resetScroll()">
                    <img :class="{'grayscale' : !verifyNumber(2)}" src="../assets/DarknessIcon2.png">
                </div>
                <div class="character" @click="selectCharacter(3);resetScroll()">
                    <img :class="{'grayscale' : !verifyNumber(3)}" src="../assets/AquaIcon.png">
                </div>
            </div>
            
        </div>
    </div>
</template>

<style>
    @import '../app.scss';

    .characters{
        position: relative;
    }
    .text_title{
        margin-top: 12rem;
        z-index: 10;
    }
    .anim_title{
        position: absolute;
        width: 80%;
    }
    .text{
        color: #4c3728;
        margin-left: 2rem;
        margin-top: 2rem;
        margin-right: 2rem;
    }
    .text-character::-webkit-scrollbar{
        width: 0;
    }
    .text-character{
        scrollbar-width: 0;
        overflow: scroll;
        font-family: 'Konosuba';
        position: absolute;
        top:10rem;
        right: 11rem;
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
        position: relative;
        width: 100%;
        height: 7rem;
        display: flex;
        justify-content: center;
        font-family: 'Konosuba';
        font-size: 6rem;
    }
    .main-content{
        margin-top: 14rem;
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