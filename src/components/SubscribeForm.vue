<template>
        <form class="subscribe-form">
            <input
                type="text" 
                class="input-text subscribe-form__input"
                placeholder="your@email.com"
                :style="{backgroundColor: dgInput, color: colorText}"
            />
            <ui-button :color="colorButton || 'primary'">Sign up</ui-button>
        </form>
</template>

<script setup>
import uiButton from '@/components/UI/Button.vue';

const props = defineProps ({
    dgInput: {
        type: String,
        required: false
    },
    colorButton: {
        type: String,
        required: false
    },
    colorText: {
        type: String,
        required: false
    },
})
</script>

<style lang="sass" scoped>
.subscribe-form
    display: flex
    justify-content: center
    @media screen and (max-width: 767px)
        justify-content: flex-start
    &__input
        @media screen and (max-width: 767px)
            padding: 0
.input-text
    max-width: 400px
</style>