<script setup>
import { RouterLink, RouterView } from "vue-router";
import HeaderTop from './components/HeaderTop.vue';
import TodoSection from './components/TodoSection.vue';
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
#sections {
  margin-top: 2rem;
  display: flex;
}
</style>

