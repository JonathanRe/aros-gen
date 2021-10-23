<template>
  <div class="max-w-2xl mx-auto px-4 pt-8">
    <h1 class="text-2xl font-semibold mb-4">aros-gen</h1>
    <button
      @click="updateCurrentLocation"
      class="mb-2 px-3 py-2 bg-indigo-500 text-white hover:bg-indigo-400"
    >
      Update
    </button>
    <LocationsSingle :location="currentLocation" />
  </div>
</template>

<script>
import locationsData from "../db.json";
import { roll } from "../modules/dice";
import LocationsSingle from "./LocationsSingle.vue";

export default {
  components: { LocationsSingle },
  data() {
    return {
      locations: locationsData,
      currentLocation: {},
    };
  },
  methods: {
    fetchRandomLocation(locations) {
      const index = roll(locations.length);
      return locations[index];
    },
    updateCurrentLocation() {
      this.currentLocation = this.fetchRandomLocation(this.locations);
    },
  },
  mounted() {
    this.updateCurrentLocation();
  },
};
</script>

<style scoped></style>
