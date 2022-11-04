<script setup>
const props = defineProps({
    isOpen: {
        type: Boolean,
        default: false
    }

})



</script>

<template>
    <div v-if='isOpen' class="modal-background" @click="$emit('close')">
        <div id="modal">
            <div id="heading">
                <slot name="heading"></slot>
            </div>
            <div id="task">
                <slot name='task'></slot>
            </div>
        </div>
    </div>
</template>

<style scoped>
.modal-background {
    background: rgba(0, 0, 0, 0.5);
    position: fixed;
    width: 100%;
    height: 100vh;
    z-index: 100;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
}

#modal {
    width: 25rem;
    height: fit-content;
    margin: auto auto;
    background-color: white;
    z-index: 101;
}
</style>