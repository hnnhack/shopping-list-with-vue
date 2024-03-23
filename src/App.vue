<script setup>
import { ref } from 'vue'

const header = ref('Shopping List App')
const items = ref([
  {id: 1, label: "10 party hats"},
  {id: 2, label: "2 board games"},
  {id: 3, label: "20 cups"}
])
const newItem = ref()
const newItemHighPriority = ref(false)
const iceCreamFlavors = ref([])
</script>

<template>
  <h1>{{ header }}</h1>
  <input v-model="newItem" type="text" placeholder="Add an item">
  {{ iceCreamFlavors }}
  <br />
  <label>
    <input type="checkbox" v-model="newItemHighPriority"> 
    High Priority
  </label>
  <br />
  <label>
    <input type="checkbox" v-model="iceCreamFlavors" value="Vanilla"> 
    Vanilla
  </label>
  <label>
    <input type="checkbox" v-model="iceCreamFlavors" value="Strawberry"> 
    Strawberry
  </label>
  <label>
    <input type="checkbox" v-model="iceCreamFlavors" value="Chocolate"> 
    Chocolate
  </label>
  <ul>
    <li v-for="({id, label}, index) in items" :key="id">
      {{ index + 1 + '-' }}
      {{label}}
    </li>
  </ul>
</template>

<style src="./main.css" lang="css"></style>