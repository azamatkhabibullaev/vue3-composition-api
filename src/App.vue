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
const newItemPriority = ref('low')
</script>

<template>
  <h1>
    {{ header }}
  </h1>
  <div class="input-group">
    <input v-model="newItem" type="text" placeholder="Add an item">
  </div>

  Priority:
  <div class="input-group">
    <input type="radio" name="priority" id="low" v-model="newItemPriority" value="low">
    <label for="low">Low</label>
  </div>
  <div class="input-group">
    <input type="radio" name="priority" id="high" v-model="newItemPriority" value="high">
    <label for="high">High</label>
  </div>
  {{ newItemPriority }}

  <ul>
    <li v-for="({ id, label }, index) in items" :key="id">
      {{ index + 1 }} - {{ label }}
    </li>
  </ul>
</template>

<style>
@import './assets/base.css';
</style>
