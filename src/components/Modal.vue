<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="[theme === 'sale' ? 'sale' : 'dark']">
            <h1>Modal Title {{ header }}</h1>
            <h3>{{ data.name }}</h3>
            <h3>{{ data.age }}</h3>
            <h3>{{ data.address }}</h3>
            <p>modal content</p>
            <button>Close Modal</button>
            <slot>Default</slot>
            <div class="links">
                <slot name="links">

                </slot>
            </div>

            
        </div>
    </div>
</template>

<script>
export default {
    name: "ModalView",
    props: {
        header: {
            type: String
        },
        data: {
            type: Object,

        },
        theme: {
            type: String
        }
    },
    methods: {
        closeModal() {
            this.$emit('close', false)
        },

    }
}
</script>

<style scoped>
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}

.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
}

h1 {
    color: red;
}

.modal.sale {
    background-color: crimson;
    color: white;
}

.modal.sale h1 {
    color: white
}

.modal.dark {
    background-color: darkolivegreen;
    color: white;
}

.modal.dark h1 {
    color: white
}
</style>