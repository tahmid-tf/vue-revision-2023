<template>
  <div>
    <button
      class="btn"
      :style="{ backgroundColor: color }"
      @click="changeValue()"
    >
      {{ text }}
    </button>
  </div>
</template>

<script>
export default {
  name: "button-component",

  data() {
    return {
      showAddTask: false,
    };
  },

  props: ["color", "text"],

  methods: {
    changeValue() {
      this.showAddTask = !this.showAddTask;
      this.$emit("showAddTask", this.showAddTask);
    },
  },
};
</script>

<style scoped></style>
