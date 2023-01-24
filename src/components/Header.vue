<template>
  <div>
    <header>
      <h1>{{ title }}</h1>

      <Buttton color="green" text="Add Task" />
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
