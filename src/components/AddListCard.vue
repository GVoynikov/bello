<script setup>
import { ref } from 'vue';
const props = defineProps({
    isOpen: {
        type: Boolean,
        default: false
    }

})
let tempHeading = ref('');


const resetTemp = () => {
    tempHeading.value = null;

}

</script>

<template>
    <div v-if='isOpen' class="modal-background">
        <div id="modal">
            <div id="inputs">


                <div id="heading">
                    <input class="form-control-plaintext heading" type='text' maxlength="333"
                        placeholder='Click to add title' v-model="tempHeading" />
                </div>

            </div>
            <div class="buttons">
                <button class="btn btn-secondary" @click="$emit('close')">Cancel</button>
                <button class="btn btn-primary mb-2" type="submit"
                    @click="$emit('add', tempHeading); resetTemp()">Submit</button>
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
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    padding: 1rem;
    width: 25rem;
    min-height: 10rem;
    margin: auto auto;
    background-color: white;
    z-index: 101;
}

.heading {
    font-family: 'Brush Script MT', cursive;
    font-size: 1.5rem;
    font-weight: bold;
}




textarea {
    width: 100%;
    height: 10rem;
}

.buttons {
    display: flex;
    justify-content: space-between;
}
</style>