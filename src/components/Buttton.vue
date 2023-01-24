<template>
  <div>
    <button class="btn" :style="{ backgroundColor: color }" @click="onClick()">
      {{ text }}
    </button>
  </div>
</template>

<script>
export default {
  name: "button-component",

  props: ["color", "text"],

  methods: {
    onClick() {
      alert("click");
    },
  },
};
</script>

<style scoped></style>
