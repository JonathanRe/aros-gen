<template>
  <div>
    <h3 class="text-xl font-semibold">
      {{ location.index }}: {{ location.name }}
    </h3>
    <p v-html="location.description"></p>
  </div>
</template>

<script>
export default {
  props: {
    location: {
      type: Object,
      required: true,
    },
  },
  setup(props) {
    return { props };
  },
  mounted() {},
};
</script>

<style scoped></style>
