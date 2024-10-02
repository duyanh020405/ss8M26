<template>
  <div>
    <h1>BAI 8 , 9</h1>
    <h2 class="text-2xl font-bold text-center mb-6">Form Đăng ký</h2>
    <form class="space-y-4" @submit.prevent="hu">
      <div>
        <label for="name" class="block text-gray-700">
          Tên:
        </label>
        <input
          v-model="user.name"
          type="text"
          id="name"
          name="name"
          class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
          required
        />
      </div>
      <div>
        <label for="email" class="block text-gray-700">
          Email:
        </label>
        <input
          v-model="user.email"
          type="email"
          id="email"
          name="email"
          class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
          required
        />
      </div>
      <div>
        <label for="password" class="block text-gray-700">
          Mật khẩu:
        </label>
        <input
          v-model="user.mk"
          type="password"
          id="password"
          name="password"
          class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
          required
        />
      </div>
      <div>
        <label for="sdt" class="block text-gray-700">
          Sdt
        </label>
        <input
          v-model="user.sdt"
          type="text"
          id="sdt"
          name="sdt"
          class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
          required
        />
      </div>
      <button
        type="submit"
        class="w-full bg-blue-500 text-white py-2 rounded-md hover:bg-blue-600 transition duration-300"
      >
        Đăng ký
      </button>
    </form>
  </div>
</template>

<script setup>
import { reactive } from "vue";

// Khởi tạo danh sách users từ localStorage nếu có
const storedUsers = localStorage.getItem("users");
const users = reactive(storedUsers ? JSON.parse(storedUsers) : []);

const user = reactive({
  name: '',
  email: '',
  mk: '',
  sdt: ''
});

const hu = () => {
  const emailExists = users.some((u) => u.email === user.email);
  
  if (emailExists) {
    alert("Email đã tồn tại, vui lòng chọn email khác.");
  } else {
    users.push({ ...user }); 
    localStorage.setItem("users", JSON.stringify(users));
    alert("Đăng ký thành công");
  }
};
</script>

<style>
</style>
