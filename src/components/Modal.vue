<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale: theme === 'sale'}">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props:
        [ 
            'theme'
        ],

        methods: 
        {
            closeModal()
            {
                this.$emit('close')
            },
        },
    }
</script>

<style>
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop{
        top: 0;
        position: fixed;
        background: #0000006b;
        width: 100%;
        height: 100%;
    }
    .modal h1{
        color: rgb(34, 108, 114);
        border-bottom: 1px solid rgb(212, 212, 212);
    }

    .modal.sale{
        background: rgb(201, 47, 75);
        color: white;
    }

    .modal.sale h1{
        color: white;
    }
</style>