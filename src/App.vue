<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Menu from './components/Menu.vue';
import Characters from './components/Characters.vue';
import About from './components/About.vue';

</script>

<template>
  <RouterView id="Home" />
  <Menu/>
  <About id="About" />
  <Characters id="Characters"/>
</template>
