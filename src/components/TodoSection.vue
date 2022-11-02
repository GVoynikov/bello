<script>
import { ref } from 'vue';
import TodoCard from './TodoCard.vue';
import ModalCard from './ModalCard.vue';

const todos = ref([]);
const isModalOpen = ref(true);



export default {
    components: {
        TodoCard,
        ModalCard

    },
    props: {
        sectionTitle: String
    }
}


</script>

<template>

    <ModalCard :isOpen='isModalOpen'>
        <template #heading>
            <h1>This is heading</h1>
        </template>
        <template #task>Taskkkk</template>
    </ModalCard>
    <div id="container">
        <h2>{{ sectionTitle }}</h2>
        <div id="cards">
            <TodoCard />
        </div>
        <button @click="">Add card</button>

    </div>

</template>

<style scoped>
main {
    width: 100%;
    display: flex;
    justify-content: around;
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