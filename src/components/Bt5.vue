<template>
  <div>
    <h1>Bài tập 5</h1>
    <p>Giới tính: {{ d }}</p>
    <p><input type="radio" v-model="d" value="Nam"> Nam</p>
    <p><input type="radio" v-model="d" value="Nữ"> Nữ</p>
    <p><input type="radio" v-model="d" value="Khác"> Khác</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const d = ref("")
</script>

<style>

</style>
