<template>
  <div class="product">
    <router-link to="/">
        <img :src="img" class="product-img" :alt="title">
    </router-link>
    <router-link to="/" class="product-name">{{ title }}</router-link>
    <span class="product-price">{{ price }}</span>
  </div>
</template>

<script setup>
const props = defineProps({
    img: {
        type: String,
        required: true
    },
    title: {
        type: String,
        required: true
    },
    price: {
        type: Number,
        required: true
    },
})
</script>

<style lang="sass" scoped>
.product
    display: flex
    flex-direction: column
    align-items: flex-start
    &-img
        width: 100%
        display: block
        margin-bottom: 24px
    &-name
        display: block
        color: #2A254B
        font-size: 20px
        text-decoration: none
        margin-bottom: 8px
        line-height: 28px
        @media screen and (max-width: 767px)
            font-size: 17px
        &:hover
            text-decoration: underline
    &-price
        display: block
        font-size: 18px
        color: #2A254B
        @media screen and (max-width: 767px)
            font-size: 17px
            
</style>