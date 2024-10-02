<template>
  <div>
    <form @submit.prevent="huhu">
      <h1>Bài tập 10</h1>
      <p>Tài khoản (Email)</p>
      <input v-model="inputEmail" type="text" placeholder="Nhập tài khoản" required>
      <p>Mật khẩu</p>
      <input v-model="inputPassword" type="password" placeholder="Nhập mật khẩu" required>
      <button type="submit">Đăng nhập</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const users = localStorage.getItem("users") ? JSON.parse(localStorage.getItem("users")) : [];
console.log("user", users);
const inputEmail = ref('');
const inputPassword = ref('');
const huhu = () => {
  const user = users.find(u => u.email === inputEmail.value && u.mk === inputPassword.value);

  if (user) {
    alert("Đăng nhập thành công!");
  } else {
    alert("Tài khoản hoặc mật khẩu không chính xác!");
  }
};
</script>

<style>
</style>
