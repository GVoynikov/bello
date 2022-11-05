<script setup>
const props = defineProps({
    isBordered: Boolean
})

</script>

<template>
    <nav>
        <h1>Bello</h1>
    </nav>

</template>

<style scoped>
nav {
    padding: 0;
    margin: 0;
    top: 0;
    height: 80px;
    width: 100%;
    background-color: #1877F2;
}

.bordered {
    border: 4px solid black;
}

h1 {
    font-size: 2.5rem;
    font-style: Pacifico;
}
</style>
