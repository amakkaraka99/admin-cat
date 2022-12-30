<script setup>
import { useAuthStore } from "../../stores/authFire";
import { computed } from "vue";
import Navbar from "../../components/Navbar.vue";

const authStore = useAuthStore();
const logout = () => {
  authStore.logout();
};
const user = computed(() => authStore.user);
</script>
<template>
  <div id="app">
    <Navbar />
    <p v-if="user">Welcome {{ user?.email }}</p>
    <button @click="logout">Logout</button>

    <router-view />
  </div>
</template>
