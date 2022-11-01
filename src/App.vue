<script setup>
import { RouterLink, RouterView } from "vue-router";
import HeaderTop from './components/HeaderTop.vue';
import TodoSection from './components/TodoSection.vue';
</script>

<template>
  <HeaderTop/>
  <TodoSection/>

  <RouterView />
</template>

