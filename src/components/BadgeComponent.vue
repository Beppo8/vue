<template>
  <div>
    <span :class="[intructorClass, (role === 'Instructor') ? instructorClass : studentClass]">{{
      role
    }}</span>
  </div>
</template>

<script>
export default {
  data: () => ({
    intructorClass: "Instructor",
    studentClass: "student",
    assistantClass: "assistant",
  }),
  props: {
    role: {
      type: String,
      required: true,
    },
  },
  emits: ["batch"],
  methods: {
    userBatch() {
      this.$emit("batch");
    },
    colorBadge() {
      if (this.role === "Instructor") {
        this.instructorClass;
      } else if (this.role === "Student") {
        this.studentClass;
      } else {
        this.assistantClass;
      }
    },
  },
};
</script>

<style>
.Instructor {
  background: #2a7dd6;
  border-radius: 4px;
  padding: 4px 8px;
  text-align: center;
  color: #fff;
}

.student {
  background: #9b51e0;
  border-radius: 4px;
  padding: 4px 8px;
  text-align: center;
  color: #fff;
}

.assistant {
  background: #CA8A35;
  border-radius: 4px;
  padding: 4px 8px;
  text-align: center;
  color: #fff;
}
</style>
