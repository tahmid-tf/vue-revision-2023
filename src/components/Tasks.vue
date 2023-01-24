<template>
  <div>
    <div v-for="task in tasks" :key="task.id">
      <h3>{{ task.text }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Task-component",
  props: {
    tasks: Array,
  },
};
</script>

<style scoped></style>
