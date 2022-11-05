<script setup>
import { RouterLink, RouterView } from "vue-router";
import { ref } from "vue";
import HeaderTop from './components/HeaderTop.vue';
import TodoSection from './components/TodoSection.vue';
import AddListCard from './components/AddListCard.vue';

const sections = ref([{
  name: 'Todo'
}, {
  name: 'In-Progress'
}, {
  name: 'Done'
}
])

const isAddListCardOpen = ref(false);
const showAddListCard = () => {
  isAddListCardOpen.value = true;
}
const closeAddListCard = () => {
  isAddListCardOpen.value = false;
}

const addCard = (tempHeading) => {
  if (tempHeading.length != 0 && tempHeading.trim().length != 0) {


    sections.value.push({
      name: tempHeading,
    })
    closeAddListCard();
  } else {
    alert('Please add title');
  }
}
</script>

<template>
  <AddListCard :isOpen="isAddListCardOpen" @add='addCard' @close="closeAddListCard" />
  <HeaderTop />
  <div id="sections">
    <TodoSection v-for="section in sections" :sectionTitle="section.name" />
    <button @click="showAddListCard" id="add" type="button" class="btn btn-dark">Add list</button>
  </div>
</template>

<style>
@font-face {
  font-family: "Pacifico";
  src: local("Pacifico"),
    url(./fonts/Pacifico-Regular.ttf) format("truetype");
}

/* @import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap'); */

#sections {
  display: flex;
  flex-wrap: wrap;
}

#add {
  display: flex;
  margin-left: 2rem;
  margin-top: 2rem;
  height: 2.5rem;
  color: white;
}
</style>

