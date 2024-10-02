<template>
  <div>
    <h1>Bai tap 4</h1>
    <p>Tien do hoan thanh : {{a}}%</p>
    <input @change="b" type="range" v-model="a">
  </div>
</template>

<script setup>
import {ref} from 'vue'
const a = ref(0)
const b =(e)=>{
    return a.value = e.target.value
}
</script>

<style>

</style>