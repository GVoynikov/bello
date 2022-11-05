<template>
    <div @click="$emit('close')" v-if="isOpen" class="info-background">
        <div class="modal">
            <h1>{{ heading }}</h1>
            <p> {{ todo }} </p>
        </div>
    </div>
</template>

<script setup>

import { ref } from 'vue';

const props = defineProps({
    heading: String,
    todo: String,
    isOpen: {
        type: Boolean,
        default: false
    }
})

</script>

<style scoped>
.info-background {
    background: rgba(0, 0, 0, 0.5);
    position: fixed;
    width: 100%;
    height: 100vh;
    z-index: 100;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
}

.modal {
    display: flex;
    justify-content: space-evenly;
    flex-direction: column;
    padding: 1rem;
    width: 25rem;
    max-height: 30rem;
    margin: auto auto;
    background-color: white;
    z-index: 100;
}
</style>