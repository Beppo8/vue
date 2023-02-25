<template>
    <div>
        <p>{{ role }} - {{ username }}</p>
    </div>
</template>

<script>
export default {
  props: {
    role: {
      type: String,
      required: true,
    },
    username: {
      type: String,
      required: true,
    },
  },
  emits: ["batch"],
  methods: {
    userBatch() {
      this.$emit("batch");
    },
  },
};
</script>
