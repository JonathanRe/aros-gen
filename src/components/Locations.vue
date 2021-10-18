<template>
  <div>
    <h1 class="text-2xl">Locations</h1>
    <ul>
      <li v-for="location in locations" :key="location.name">
        {{ location.name }}
      </li>
      <p class="mt-4">{{ locations[locationIndex].name }}</p>
      <button class="bg-indigo-500" @click="setLocationIndex()">Reroll</button>
    </ul>
  </div>
</template>

<script>
import locationsData from "../db.json";
import { roll } from "../modules/dice";

export default {
  data() {
    return {
      locations: locationsData,
      locationIndex: roll(12),
    };
  },
  methods: {
    setLocationIndex() {
      this.locationIndex = roll(12);
    },
  },
  mounted() {},
};
</script>

<style scoped></style>
