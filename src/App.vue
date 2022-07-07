<script setup>
import { ref } from 'vue'

const header = ref('Shopping List App')

const items = ref([
  // { id: 1, label: '10 party hats' },
  // { id: 2, label: '20 cups' },
  // { id: 3, label: '10 gaming chairs' },
  // { id: 3, label: '1 Awesome Vue Course' }
])

const newItem = ref('')
const newItemHighPriority = ref(false)

const saveItem = () => {
  items.value.push({
    id: items.value.length + 1,
    label: newItem.value
  })
  newItem.value = ''
}

const editing = ref(false)

const doEdite = (e) => {
  editing.value = e
  newItem.value = ''
}
</script>

<template>
  <div class="header">
    <h1>{{ header }}</h1>
    <button class="btn" v-if="editing" @click="doEdite(false)">Cancel</button>
    <button class="btn btn-primary" v-else @click="doEdite(true)">Add Item</button>
  </div>

  <form class="add-item-form" v-if="editing" @submit.prevent="saveItem">
    <div class="input-group">
      <div>
        <input v-model.trim="newItem" type="text" placeholder="Add an item">
      </div>

      <div>
        <input type="checkbox" id="priority" v-model="newItemHighPriority">
        <label for="priority">High Priority</label>
      </div>
    </div>

    <button class="btn btn-primary" type="submit">Save</button>
  </form>

  <ul>
    <li v-for="({ id, label }, index) in items" :key="id" class="item">
      {{ index + 1 }} - {{ label }}
    </li>
  </ul>

  <p v-if="!items.length">
    Nothing to see here
  </p>
</template>

<style>
@import './assets/base.css';
</style>
