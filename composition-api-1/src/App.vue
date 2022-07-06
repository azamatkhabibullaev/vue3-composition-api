<script setup>
import { ref } from 'vue'

const msg = ref('Hello World!')
</script>

<template>
  <h1>
    {{ msg.toUpperCase() }}
    <!-- {{ msg.toUpperCase(); msg.toLowerCase() }} -->
    <!-- {{ const sum = 42; }} -->
    <!-- {{ if(msg) { return 'Welcome!' } }} -->
    {{ msg ? msg : 'Welcome!' }}
    {{ msg || 'Welcome!' }}
  </h1>
  <input type="text" v-model="msg">
  <!-- <input type="text" v-model="msg.toUpperCase()"> you cannot use .toUpperCase() inside v-model -->
</template>

<style>
@import './assets/base.css';
</style>
