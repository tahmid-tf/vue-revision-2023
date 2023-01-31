<template>
  <div>
    <header>
      <h1>{{ title }}</h1>

      <Buttton color="green" text="Add Task" @showAddTask="showAddTask" />
    </header>
  </div>
</template>

<script>
import Buttton from "@/components/Buttton";

export default {
  name: "Header-Component",
  components: {
    Buttton,
  },

  methods: {
    showAddTask(data) {
      this.$emit("showAddTask", data);
    },
  },

  props: {
    title: {
      type: String,
      default: "Hello World",
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
