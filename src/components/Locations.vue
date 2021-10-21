<template>
  <div class="max-w-2xl mx-auto">
    <h1 class="text-3xl font-bold">aros-gen</h1>
    <!-- <ul>
      <li v-for="location in locations" :key="location.index">
        <span>{{ location.index }}:</span> {{ location.name }}
      </li>
    </ul> -->
    <h2 class="mt-6 text-xl font-bold">Location</h2>
    <h3 class="mt-2 font-bold">Rolled:</h3>
    <p>
      {{ locations[randomLocationIndex].index }}:
      {{ locations[randomLocationIndex].name }}
    </p>
    <p>
      {{ locations[randomLocationIndex].description }}
    </p>
    <button
      class="mt-4 p-2 text-white bg-indigo-500 hover:bg-indigo-400"
      @click="setRandomLocationIndex()"
    >
      Reroll
    </button>
  </div>
</template>

<script>
import locationsData from "../db.json";
import { roll } from "../modules/dice";

export default {
  data() {
    return {
      locations: locationsData,
      randomLocationIndex: roll(12),
    };
  },
  methods: {
    setRandomLocationIndex() {
      this.randomLocationIndex = roll(12);
    },
  },
  mounted() {},
};
</script>

<style scoped></style>
