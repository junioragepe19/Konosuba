<script>
    export default {
        data(){
            return{
            texto: "'Konosuba' é uma série japonesa de light novels escrita por Natsume Akatsuki e ilustrada por Kurone Mishima." + 
                " A história segue as aventuras cômicas de Kazuma Satou, um adolescente que morre de forma ridícula e acaba sendo" +
                " transportado para um mundo de fantasia semelhante a um jogo de RPG." + "\n" +
                "No novo mundo, Kazuma se encontra com a deusa Aqua e é oferecida a ele a oportunidade de renascer nesse mundo e derrotar " +
                "o Rei Demônio. No entanto, ele só pode levar consigo uma única coisa. Kazuma escolhe levar Aqua com ele, pensando que " +
                "ela seria uma deusa poderosa, mas acaba descobrindo que ela é uma deusa inútil e incompetente. Logo após sua chegada, " +
                "Kazuma forma uma equipe com outras garotas problemáticas: Megumin, uma feiticeira obcecada por explosões, e Darkness, " +
                "uma cavaleira masoquista que adora apanhar em batalha. Juntos, eles enfrentam missões perigosas e encontram personagens " +
                "excêntricos enquanto tentam ganhar dinheiro e fama para sobreviver nesse mundo."
            };
        },
        mounted() {
        const observer = new IntersectionObserver((entries) => {
        const [entry] = entries;
        if (entry.isIntersecting) {
            this.startTypingEffect();
            observer.disconnect();
        }
        });

        observer.observe(this.$refs.targetElement);
        },
        methods: {
            
            startTypingEffect() {
                console.log(this.texto.length);
            let index = 0;
            const typingElement = document.getElementById("text");
            const timer = setInterval(() => {
                if (index >= this.texto.length) {
                clearInterval(timer);
                return;
                }
                typingElement.textContent += this.texto.charAt(index);
                index++;
            }, 50);
            }
        }
};
</script>

<template>
    <div class="main">
        <img class="img_main" src="../assets/konosubaBackGround.jpeg">
        <div ref="targetElement"></div>
        <h2 class="texto" id="text"></h2>
    </div>
</template>

<style>

@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@700&display=swap');

    .main{
        margin-top: -1rem;
        display: flex;
        position: relative;
        width: 100%;
        padding: 2rem;
        height: 60rem;
        display: flex;
    }
    .texto{
        font-size: 2rem;
        color: white;
        z-index: 100;
        font-family: 'Josefin Sans';
        margin: 2rem;
        margin-top: 0;
        text-indent: 1rem;
    }
    .img_main{
        top: 0;
        position: absolute;
        width: 100%;
        height: 100%;
        filter: brightness(20%)
    }
</style>