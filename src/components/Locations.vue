<template>
  <div>
    <h1 class="text-2xl">Locations</h1>
    <ul>
      <li v-for="location in locations" :key="location.name">
        {{ location.name }}
      </li>
      <p class="mt-4">{{ locations[0].name }}</p>
    </ul>
  </div>
</template>

<script>
import locationsData from "../db.json";

export default {
  data() {
    return {
      locations: locationsData,
    };
  },
};
</script>

<style scoped></style>
