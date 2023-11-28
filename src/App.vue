<script setup lang="ts">
import ProductCard from '@/components/ProductCard.vue'
import { product } from '@/ts/constants'

const addToCart = (product: any) => {
  console.log('Add to cart', product)
}
</script>

<template>
  <ProductCard :product="product" @add-to-cart="addToCart(product)" />
</template>
