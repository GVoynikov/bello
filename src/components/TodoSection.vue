<script>
import { ref } from 'vue';
const todos = ref([]);



</script>

<template>

<main>
    <ul id="todo">

    </ul>
    <ul id="in-progress"></ul>
    <ul id='done'></ul>
</main>

</template>

<style scoped>
main {
    width: 100%;
    display: flex;
    justify-content: around;
    gap: 2rem;
}

ul {
    min-width: 25rem;
    min-height: 40rem;
    border: 2px solid black;
}
</style>