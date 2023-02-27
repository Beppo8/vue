<template>
  <button @click="emitEvent">
    ADD
    <slot></slot>
  </button>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    variant: {
      type: String,
      default: "blue",
    },
  },
  emits: ["click"],
  methods: {
    emitEvent() {
      this.$emit("click");
    },
  },
});
</script>

<style></style>
