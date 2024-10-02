<template>
  <div> 
    <h1>Bài tập 2</h1>
    <p>Color: {{ b }}</p>
    <div :style="{ backgroundColor: b, width: '100px', height: '100px', border: '1px solid black' }">
    </div>
    <input @input="c" type="text" v-model="a" placeholder="Nhập mã màu">
    <button @click="submit">Submit</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const a = ref('')
const b = ref('')
const submit = () => {
    b.value = a.value
}

const c = (e) => {
    a.value = e.target.value
}
</script>

