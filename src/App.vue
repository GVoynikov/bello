<script setup>
import { RouterLink, RouterView } from "vue-router";
import { ref } from "vue";
import HeaderTop from './components/HeaderTop.vue';
import TodoSection from './components/TodoSection.vue';
import ModalCard from './components/ModalCard.vue';


</script>

<template>

  <HeaderTop />
  <div id="sections">
    <TodoSection sectionTitle='Todo' />
    <TodoSection sectionTitle='In-Progress' />
    <TodoSection sectionTitle='Done' />
  </div>
  <RouterView />
</template>

<style>
@font-face {
  font-family: "Pacifico";
  src: local("Pacifico"),
    url(./fonts/Pacifico-Regular.ttf) format("truetype");
}

/* @import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap'); */

#sections {
  margin-top: 2rem;
  display: flex;
  flex-wrap: wrap;
}
</style>

