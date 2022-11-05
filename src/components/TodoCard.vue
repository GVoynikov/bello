<script setup>

import InfoBox from './InfoBox.vue';
import { ref } from 'vue';

const props = defineProps({
    heading: {
        type: String,
        default: 'New todo'
    },

    todo: {
        type: String,
        default: 'Add description'
    },

    id: {
        type: Number,
        default: null
    },

    draggable: null
},)

const isInfoOpen = ref(false);
const closeInfoBox = () => {
    isInfoOpen.value = false;
}

const dragStart = (e) => {
    const target = e.target;
    e.dataTransfer.setData('card_id', target.id);

    setTimeout(() => {
        target.style.display - 'none';
    }, 1)
}

</script>

<template>
    <InfoBox @close="closeInfoBox" :isOpen="isInfoOpen" :heading="heading" :todo="todo" />
    <div @click="isInfoOpen = true" class="card" :id='id' :draggable="draggable" @dragstart='dragStart' @dragover.stop>
        <h2>{{ heading }}</h2>
    </div>
</template>

<style scoped>
.card {
    background-color: white;
    border-radius: 0.5rem;
    margin-top: 0.5rem;
    box-shadow: 2px 2px 8px;
    display: flex;
    max-width: 368px;
    padding-left: 1rem;
}

.card:hover {
    opacity: 0.8;
}


h2 {
    font-weight: 600;
}
</style>