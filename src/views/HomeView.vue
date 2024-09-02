<script setup lang="ts">
import {ref} from 'vue'
// import TheWelcome from '../components/TheWelcome.vue'
type restaurant ={
  name: string
  staus: string
}
const restaurants: restaurant[] = ref([
  'KFC', 'Chicken Tonight', 'Cafe Javas'
])
</script>

<template>
  <main>
    <!-- <TheWelcome /> -->
     <div class="h3 text-gray-600 text-underline font-semibold text-center pt-5">
      <ul>
        <li v-for="restaurant in restaurants" :key="restaurant.name">
          {{ restaurant.name }}
        </li>
      </ul>
     </div>
     <pre>
      {{restaurants}}
     </pre>

  </main>
</template>
