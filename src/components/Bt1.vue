<template>
  <div> 
    <h1>Bai tap 1</h1>
    <p>Input : {{b}} </p>
        <input @change="c" type="text" v-model="b">
        <button @click="submit">Submit</button>
  </div>
</template>

<script setup>
import {ref} from 'vue'
const a = ref('')
const b = ref('')
const submit =()=>{
    b.value = a.value
}
const c =(e)=>{
    return e.target.value
}
</script>

<style>

</style>