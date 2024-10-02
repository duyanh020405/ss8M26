<template>
  <div>
    <h1>Bai tap 7</h1>
    <form @submit.prevent="saveProduct">
      <label for="fname">Ma san pham:</label>
      <br />
      <input type="text" v-model="product.horse" />
      <br />
      <label for="lname">Ten san pham:</label>
      <br />
      <input type="text" v-model="product.name" />
      <br />
      <label for="price">Gia san pham:</label>
      <br />
      <input type="number" v-model="product.price" />
      <br />
      <label for="quantity">So luong:</label>
      <br />
      <input type="number" v-model="product.quantity" />
      <br />
      <button type="submit">Local goooo</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const product = ref({
  horse: '',
  name: '',
  price: 0,
  quantity: 0
})

const saveProduct = () => {
  console.log(product.value)
}
</script>

<style>
</style>
