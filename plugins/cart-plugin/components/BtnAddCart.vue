<template>
    <button class="float-right btn btn-primary" @click="addCart" :disabled="IsInCart">
        <svg class="bi bi-bag-fill" width="1em" height="1em" viewBox="0 0 16 16" fill="currentColor"
             xmlns="http://www.w3.org/2000/svg">
            <path d="M1 4h14v10a2 2 0 01-2 2H3a2 2 0 01-2-2V4zm7-2.5A2.5 2.5 0 005.5 4h-1a3.5 3.5 0 117 0h-1A2.5 2.5 0 008 1.5z"/>
        </svg>
    </button>
</template>

<script>
    export default {
        name: "BtnAddCart",
        props: {
            pet: null,
        },
        computed: {
            IsInCart() {
                return this.$store.getters.cart.find(pet => pet.id == this.pet.id)
            }
        },
        methods : {
            addCart : function () {
                this.$store.commit('addCart', this.pet)
            }
        }
    }
</script>
