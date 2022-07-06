<script setup>
import { ref } from 'vue'

const header = ref('Shopping List App')

const items = ref([
  {id: 1, label: '10 party hats'},
  {id: 2, label: '20 cups'},
  {id: 3, label: '10 gaming chairs'},
  {id: 3, label: '1 Awesome Vue Course'}
])
</script>

<template>
  <h1>
    {{ header }}
  </h1>
  <ul>
    <li
      v-for="({id, label}, index) in items"
      :key="id"
    >
      {{ index + 1 }} - {{ label }}
    </li>
  </ul>
</template>

<style>
@import './assets/base.css';
</style>
