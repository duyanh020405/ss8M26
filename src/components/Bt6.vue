<template>
  <div>
    <h1>Bài tập 6</h1>
    <p>Sở thích: {{ a }}</p>
    <input @click="hu" type="checkbox" value="Đá bóng"> Đá bóng
    <input @click="hu" type="checkbox" value="Bóng chuyền"> Bóng chuyền
    <input @click="hu" type="checkbox" value="Code"> Code
    <input @click="hu" type="checkbox" value="Bơi lội"> Bơi lội
  </div>
</template>

<script setup>
import { ref } from 'vue'
const a = ref([])
const hu = (e) => {
    const value = e.target.value
    if (e.target.checked) {
        a.value.push(value)
    } 
    else {
        a.value = a.value.filter(item => item !== value)
    }
}
</script>

<style>

</style>
