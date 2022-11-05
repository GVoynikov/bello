<script setup>
import { VueElement } from 'vue';
import { ref } from 'vue';
const props = defineProps({
    isOpen: {
        type: Boolean,
        default: false
    }

})
let tempHeading = ref('');
let tempTodo = ref('');

const resetTemp = () => {
    tempHeading.value = null;
    tempTodo.value = null;
}

</script>

<template>
    <div v-if='isOpen' class="modal-background">
        <div id="modal">
            <div id="heading">
                <input type='text' maxlength="28" placeholder='add heading' v-model="tempHeading" />
            </div>
            <div id="task">
                <input type='textarea' placeholder='add todo' v-model="tempTodo" />
            </div>
            <button @click="$emit('close')">Close</button>
            <button type="submit" @click="$emit('add', tempHeading, tempTodo); resetTemp()">Submit</button>

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