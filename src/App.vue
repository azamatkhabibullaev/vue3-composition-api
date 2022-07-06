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
const newItemHighPriority = ref(false)
const iceCreamFlavors = ref([])
</script>

<template>
  <h1>
    {{ header }}
  </h1>
  <div class="input-group">
    <input v-model="newItem" type="text" placeholder="Add an item">
  </div>

  <div class="input-group">
    <input type="checkbox" id="priority" v-model="newItemHighPriority">
    <label for="priority">High Priority</label>
  </div>

  <div>{{ newItemHighPriority }}</div>

  <div class="input-group">
    <div>
      <input type="checkbox" id="vanilla" v-model="iceCreamFlavors" value="vanilla">
      <label for="vanilla">Vanilla</label>
    </div>
    <div>
      <input type="checkbox" id="chocolate" v-model="iceCreamFlavors" value="chocolate">
      <label for="chocolate">Chocolate</label>
    </div>
    <div>
      <input type="checkbox" id="strawberry" v-model="iceCreamFlavors" value="strawberry">
      <label for="strawberry">Strawberry</label>
    </div>
  </div>
  
  <div>{{ iceCreamFlavors }}</div>

  <ul>
    <li v-for="({ id, label }, index) in items" :key="id">
      {{ index + 1 }} - {{ label }}
    </li>
  </ul>
</template>

<style>
@import './assets/base.css';
</style>
