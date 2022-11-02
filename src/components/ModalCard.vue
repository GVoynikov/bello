<script>
export default {
    props: {
        isOpen: {
            type: Boolean,
            default: false
        }

    }
}



</script>

<template>
    <div v-if='isOpen' class="modal-background">
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
    background: rgba(0, 0, 0, 0.3);
    position: fixed;
    width: 100%;
    height: 100vh;
    z-index: 100;
    top: 0;
    left: 0;
}

#modal {
    background-color: white;
}
</style>