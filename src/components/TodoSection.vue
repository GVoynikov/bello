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

    sectionTitle: String,
    id: null
});

const showModal = () => {
    isModalOpen.value = true;
}
const closeModal = () => {
    isModalOpen.value = false;
}

const drop = (e) => {
    const card_id = e.dataTransfer.getData('card_id');

    const card = document.getElementById(card_id);

    card.style.display = 'block';

    e.target.appendChild(card);
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
        <div id="heading">
            <h2>{{ sectionTitle }}</h2>
            <svg xmlns="http://www.w3.org/2000/svg" width="30" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                stroke="currentColor" class='add' @click="showModal">
                <path stroke-linecap="round" stroke-linejoin="round"
                    d="M12 9v6m3-3H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z" />
            </svg>
        </div>



        <div :id="id" class="cards" @dragover.prevent @drop.prevent="drop">
            <TodoCard v-for='todo in todos' :heading='todo.heading' :todo='todo.todo' :id="todo.id" :key='todo.id'
                draggable="true" />
        </div>

    </div>

</template>

<style scoped>
h2 {
    font-family: 'Pacifico', cursive;
}

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
    margin-top: 2rem;
    min-width: 25rem;
    min-height: 40rem;
    background-color: lightgray;
}

button {
    width: 7rem;

}

.cards {
    height: 100%;
    display: flex;
    flex-direction: column;
}

#heading {
    max-height: 3rem;
    display: flex;
    justify-content: space-between;
}

.add:hover {
    opacity: 0.5;
}
</style>