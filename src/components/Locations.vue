<template>
  <div class="max-w-2xl mx-auto">
    <h1 class="text-3xl font-bold">aros-gen</h1>
    <button
      class="mt-8 p-2 text-white bg-indigo-500 hover:bg-indigo-400"
      @click="setRandomLocationIndex()"
    >
      Reroll
    </button>
    <h2 class="mt-4 text-xl font-bold">Location</h2>
    <p>
      {{ locations[randomLocationIndex].index }}:
      {{ locations[randomLocationIndex].name }}
    </p>
    <div>
      {{ locations[randomLocationIndex].description }}
    </div>
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
