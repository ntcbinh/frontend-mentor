<script setup lang="ts">
import type { PropType } from 'vue'

interface IProduct {
  type: string
  name: string
  information: string
  price: number
  salePrice: number
}
defineProps({
  product: {
    type: Object as PropType<IProduct>,
    required: true
  }
})
defineEmits(['add-to-cart'])
const formatPrice = (price: number) => {
  return `$${price}`
}
</script>
<template>
  <div class="product-card">
    <div class="card">
      <div class="image" />
      <div class="description">
        <div class="type">{{ product.type }}</div>
        <div class="name">{{ product.name }}</div>
        <div class="info">{{ product.information }}</div>
        <div class="price">
          <div class="sale-price">{{ formatPrice(product.salePrice) }}</div>
          <div class="normal-price">{{ formatPrice(product.price) }}</div>
        </div>
        <div>
          <button class="add-to-cart btn" @click="$emit('add-to-cart')">
            <img src="/src/assets/images/icons8-cart-50.png" alt="cart-icon" />Add to cart
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
