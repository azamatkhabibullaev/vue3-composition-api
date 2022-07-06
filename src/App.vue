<script setup>
import { ref } from 'vue'

const header = ref('Shopping List App')

const items = ref([
  { id: 1, label: '10 party hats' },
  { id: 2, label: '20 cups' },
  { id: 3, label: '10 gaming chairs' },
  { id: 3, label: '1 Awesome Vue Course' }
])

const newItem = ref('')
</script>

<template>
  <h1>
    {{ header }}
  </h1>
  <input v-model.lazy="newItem" type="text" placeholder="Add an item">
  <!-- lazy, trim, number, enter -->
  <br>
  {{ newItem }}
  <ul>
    <li v-for="({ id, label }, index) in items" :key="id">
      {{ index + 1 }} - {{ label }}
    </li>
  </ul>
</template>

<style>
@import './assets/base.css';
</style>
