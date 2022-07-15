<script setup lang="ts">
import axios from "axios";
import { ref } from "vue";

const login = ref("test@tglobal.pro");
const password = ref("tpassword");

const fetchUser = async () => {
  const response = await axios.post("http://localhost:8081/auth", {
    login: login.value,
    password: password.value,
  });
};
</script>

<template>
  <div class="form">
    <input type="email" v-model="login" />
    <input type="password" v-model="password" />
    <button class="btn" @click="fetchUser">fetch user</button>
  </div>
</template>

<style>
.form {
  display: flex;
  flex-direction: column;
}

input {
  padding: 10px;
  margin-bottom: 10px;
}

button {
  padding: 10px;
}
</style>
