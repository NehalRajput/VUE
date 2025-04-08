<script setup>
import { ref } from 'vue'
import Blue from './assets/images/socks_blue.jpg'
import Green from './assets/images/socks_green.jpg'

const product = 'Socks'
const image = ref('./images/socks_green.jpg') 
const inStock = true
const cart = ref(0)

const details = ['50% cotton', '30% wool', '20% polyester']

const variants = [
  {
    id: 2234,
    color: 'green',
    image: Green
  },
  {
    id: 2235,
    color: 'blue',
    image: Blue
  }
]

function addToCart() {
  cart.value += 1
}

function updateImage(newImage) {
  image.value = newImage
}
</script>

<template>
  <div>
    <div class="nav-bar"></div>

    <div class="product-display">
      <div class="container">
     
        <div class="cart">Cart({{ cart }})</div>

        <div class="product-image">
          <img :src="image" alt="Product image" />
        </div>

        <div class="product-info">
          <h1>{{ product }}</h1>
          <p v-if="inStock">In Stock</p>
          <p v-else>Out of Stock</p>

          <ul>
            <li v-for="detail in details" :key="detail">{{ detail }}</li>
          </ul>


          <div v-for="variant in variants" :key="variant.id" class="color-circle"
            :style="{ backgroundColor: variant.color }" @mouseover="updateImage(variant.image)">
          </div>


          <button class="button" @click="addToCart">Add to Cart</button>
        </div>
      </div>
    </div>
  </div>
</template>
