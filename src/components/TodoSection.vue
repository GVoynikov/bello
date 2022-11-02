<script>
import { ref } from 'vue';
import TodoCard from './TodoCard.vue';
const todos = ref([]);

export default {
    components: {
        TodoCard
    },
    props: {
        sectionTitle: String
    }
}


</script>

<template>

    <main>
        <div id="container">
            <h2>{{ sectionTitle }}</h2>
            <div id="cards">
                <TodoCard />
            </div>
            <button>Add card</button>

        </div>
    </main>

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