<script setup>
import { RouterView } from 'vue-router';
</script>

<template>
  <nav>
    <RouterLink to="/">Home</RouterLink> | 
    <RouterLink to="/login">Login</RouterLink> |
    <RouterLink to="/register">Register</RouterLink>
  </nav>
  <RouterView/>
</template>