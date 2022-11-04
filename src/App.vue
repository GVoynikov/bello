<script setup>
import { RouterLink, RouterView } from "vue-router";
import { ref } from "vue";
import HeaderTop from './components/HeaderTop.vue';
import TodoSection from './components/TodoSection.vue';
import ModalCard from './components/ModalCard.vue';

let hasBorder = ref(true)
</script>

<template>

  <HeaderTop :isBordered="hasBorder" />
  <div id="sections">
    <TodoSection sectionTitle='Todo' />
    <TodoSection sectionTitle='In-Progress' />
    <TodoSection sectionTitle='Done' />
  </div>
  <RouterView />
</template>

<style>
#sections {
  margin-top: 2rem;
  display: flex;
}
</style>

