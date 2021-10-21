<template>
  <p>{{ index }}: {{ name }}</p>
  <div v-html="content"></div>
</template>

<script>
export default {
  data() {
    return {
      index: locationData.index,
      name: locationData.name,
      content: locationData.description,
    };
  },
};

defineProps({
  locationData: Object,
});
</script>

<style scoped></style>
