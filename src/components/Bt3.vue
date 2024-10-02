<template>
  <div>
    <h1>Bai tap 3</h1>
    <p>Date :{{a}}</p>
    <input @change="handleDate" type="date" v-model="b">
    <button @click="submit">Submit</button>
  </div>
</template>

<script setup>
import {ref} from 'vue'
const a = ref('')
const b = ref('')
const submit =()=>{
    a.value = b.value
}
const handleDate =(e)=>{
    return e.target.value
}
</script>

<style>

</style>