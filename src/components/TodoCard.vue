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
    }
})

</script>

<template>
    <div id="card">
        <h2>{{ heading }}</h2>
        <p>{{ todo }}</p>
        <p>{{ id }}</p>
    </div>
</template>

<style scoped>
#card {
    background: white;
}
</style>