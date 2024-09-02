<script setup lang="ts">
import { ref, type Ref } from "vue";
// import TheWelcome from '../components/TheWelcome.vue'
type restaurant = {
  name: string;
  status: string;
};
const restaurants: Ref<restaurant[]> = ref([
  { name: "KFC", status: "Very Good" },
  { name: "Cafe Javas", status: "Good" },
  { name: "Cafe Javas", status: "Fair" },
]);

const newRestaurantName = ref("");
const newRestaurantStatus = ref("")

const addRestaurant = () => {
  restaurants.value.push({
    name: newRestaurantName.value,
    status: newRestaurantStatus.value,
  });
  newRestaurantName.value = ''
  newRestaurantStatus.value= ''
};
</script>

<template>
  <main>
    <div class="justify-center flex pt-4">
      <form action="" @submit.prevent="addRestaurant" class="block">
        <label for="restaurant">Add new restaurant</label>
        <br>
        <input
          type="text"
          v-model="newRestaurantName"
          placeholder="Add restaurant name"
          class="border border-gray-600 mr-3 text-center"
        />
        <input type="text"
        v-model="newRestaurantStatus"
        placeholder="Add Restaurant status"
        class="border border-gray-600 mr-3 text-center">
        <button class="bg-blue-500 font-semibold text-white rounded-md p-1">Add Restaurant</button>
      </form>
    </div>
    <!-- <TheWelcome /> -->
    <div class="h3 text-gray-600 text-underline font-semibold text-center pt-5">
      <ul>
        <pre>
        {{ newRestaurant }}
        </pre>
        <li
          class="table-fixed mt-5 w-full text-center justify-center"
        >
        <table class="w-full border-collapse border border-gray-300">
          <thead>
            <tr class="bg-amber-900 text-white">
              <th>Name</th>
              <th>Status</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="restaurant in restaurants"
            :key="restaurant.name">
              <td>{{ restaurant.name }}</td>
              <td>{{ restaurant.status }}</td>
            </tr>
          </tbody>
        </table>
        </li>

        <!-- <table class="table-fixed mt-5 w-full text-center justify-center">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>{{ restaurant.name }}</td>
      <td>{{restaturant.status}}</td>
    </tr>
  </tbody>
</table> -->
      </ul>
    </div>

    <!-- <pre class="bg-amber-100 flex justify-center">
      {{restaurants}}
     </pre> -->
  </main>
</template>
