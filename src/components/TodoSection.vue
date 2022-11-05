<script setup>
import { ref } from 'vue';
import TodoCard from './TodoCard.vue';
import ModalCard from './ModalCard.vue';

const getId = () => {
    return Math.floor(Math.random() * 100000);
}

const todos = ref([]);
const isModalOpen = ref(false);


const addTodo = (tempHeading, tempTodo) => {
    todos.value.push({
        id: Math.floor(Math.random() * 10000000000),
        heading: tempHeading,
        todo: tempTodo
    })
    closeModal();
}



const props = defineProps({

    sectionTitle: String
});

const showModal = () => {
    isModalOpen.value = true;
}
const closeModal = () => {
    isModalOpen.value = false;
}

</script>

<template>

    <ModalCard :isOpen='isModalOpen' @close="closeModal" @add="addTodo">
        <template #heading>
            <h1>This is heading</h1>
        </template>
        <template #task>Taskkkk</template>
    </ModalCard>
    <div id="container">
        <h2>{{ sectionTitle }}</h2>
        <div id="cards">
            <TodoCard v-for='todo in todos' :heading='todo.heading' :todo='todo.todo' :id="todo.id" :key='todo.id' />
        </div>
        <button @click="showModal">Add card</button>

    </div>

</template>

<style scoped>
main {
    width: 100%;
    display: flex;
    justify-content: space-around;
    gap: 2rem;
}

#container {
    display: flex;
    padding: 1rem;
    flex-direction: column;
    justify-content: space-between;
    margin-left: 2rem;
    min-width: 25rem;
    min-height: 40rem;
    background-color: lightgray;
}

button {
    width: 7rem;

}

#cards {
    height: 100%;
    display: flex;
    flex-direction: column;
}
</style>