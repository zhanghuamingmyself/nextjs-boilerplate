
<script setup>
import { ref } from 'vue';
// import { getDatabaseConnection } from '../services/db';
// import {User} from "../entities/User";
//
const users = ref([]);
//
// async function fetchUsers() {
//   const connection = await getDatabaseConnection();
//   const userRepository = connection.getRepository(User);
//   users.value = await userRepository.find();
// }
//
// console.log("qewqerert123")
// fetchUsers();
// // 在服务器端渲染期间调用 fetchUsers
if (import.meta.env.SSR) {
  users.value = [{
    id:1,
    name:'qwew'
  }]
}

const handleMessage = () => {
  message.info("This is a normal message");
}
</script>

<template>
  <div>
    <div>
      <a-button @click="handleMessage">
        button
      </a-button>
      <h1>Users</h1>
      <ul>
        <li v-for="user in users" :key="user.id">{{ user.name }}</li>
      </ul>
    </div>
    <nav>
      <ul>
        <li><NuxtLink to="/about">About</NuxtLink></li>
        <li><NuxtLink to="/posts/1">Post 1</NuxtLink></li>
        <li><NuxtLink to="/posts/2">Post 2</NuxtLink></li>
      </ul>
    </nav>
  </div>
</template>
<style scoped>

</style>