<template>
    <button
        v-if="type === 'button'"
        :class="['btn',
            {
            'btn--primary': color === 'primary',
            'btn--secondary': color === 'secondary',
            'btn--lightgray': color === 'lightgray',
            'btn--fullWidth': mobileFullWidth,
            },
        ]">
        <slot />
    </button>
    <router-link v-else
        :to="to"
        :class="['btn',
            {
            'btn--primary': color === 'primary',
            'btn--secondary': color === 'secondary',
            'btn--lightgray': color === 'lightgray',
            'btn--fullWidth': mobileFullWidth,
            },
        ]">
        <slot />
    </router-link>
</template>

<script setup>
const props = defineProps({
    background: {
        type: String,
        required: false
    },
    type: {
        type: String,
        default: 'button'
    },
    to: {
        type: String,
        required: false
    },
    color: {
        type: String,
        default: 'primary'
    },
    mobileFullWidth: {
        type: Boolean,
        default: false
    }
})

</script>

<style lang="sass" scoped>

.btn
    padding: 0 32px
    display: inline-flex
    align-items: center
    justify-content: center
    cursor: pointer
    border: none
    font-size: 16px
    height: 56px
    text-decoration: none
    white-space: nowrap
    &:hover
        opacity: 0.8
    &--primary
        background: #2A254B
        color: #fff
    &--secondary
        background: rgba(249, 249, 249, 0.15)
        color: #fff
    &--lightgray
        background: #F9F9F9
        color: #2A254B
    &--white
        background: #fff
        color: #2A254B
    &--fullWidth
        @media screen and (max-width: 767px)
            width: 100%
</style>