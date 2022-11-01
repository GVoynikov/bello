<script>
export default {
    name: 'HeaderTop',
    data () {
        return {
            isBordered: false,
        }
    }
}

</script>

<template>
    <ul v-bind:class='{bordered: isBordered}'>
        <li>Home</li>
        <li>About</li>
    </ul>

</template>

<style scoped>
    ul {
        padding: 0;
        margin: 0;
        top: 0;
        height: 80px;
        width: 100%;
        background-color: blue;
    }

    .bordered {
        border: 4px solid black;
    }
</style>
