<script setup>

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

const dragStart = (e) => {
    const target = e.target;
    e.dataTransfer.setData('card_id', target.id);

    setTimeout(() => {
        target.style.display - 'none';
    }, 1)
}

</script>

<template>
    <div class="card" :id='id' :draggable="draggable" @dragstart='dragStart' @dragover.stop>
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
    align-items: center;
    padding-left: 1rem;
}


h2 {
    font-weight: 600;
}
</style>