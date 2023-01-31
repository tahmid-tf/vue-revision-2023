<template>
  <div>
    <div v-for="task in tasks" :key="task.id">
      <Task
        :task="task"
        @toggle-reminder="$emit('toggle-reminder', task.id)"
        @delete-task="$emit('delete-task', task.id)"
      ></Task>
    </div>
  </div>
</template>

<script>
import Task from "@/components/Task";

export default {
  name: "Tasks-component",
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },

  methods: {},

  emits: ["delete-task", "toggle-reminder"],
};
</script>

<style scoped></style>
