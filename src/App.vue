<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Menu from './components/Menu.vue';
import Characters from './components/Characters.vue';
import TransitionSession from './components/TransitionSession.vue';
</script>

<template>
  <RouterView />
  <!-- <Menu /> -->
  <TransitionSession />
  <Characters/>
</template>
