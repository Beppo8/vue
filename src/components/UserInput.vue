<template>
  <div>
    <h2>Username</h2>
    <input v-model="newUser.name" type="text" />
    <p v-if="newUser.name.length === 0">Cannot be empty</p>
    <select v-model="newUser.role">
        <option v-for="option in options" :value="option.value">
          {{ option.text }}
        </option>
    </select>
    <UserButton v-bind:variant="''" @click="addNewUser" />
    <h1>{{ userList }}</h1>
    <hr>
    <h2>Batch</h2>
    <BatchComponent :username="newUser.name" :role="newUser.role" />
  </div>
</template>

<script>
import UserButton from "./UserButton.vue";
import BatchComponent from "./BatchComponent.vue";
import { defineComponent } from "vue";

export default defineComponent({
  components: {
    BatchComponent,
    UserButton,
  },
  data: () => ({
    newUser: {
      name: "Saul",
      role: "Student",
      creation_date: "",
    },
    userList: [
      {
        name: "Pedrito",
        role: "Instructor",
        creation_date: "16-24-23 15:23",
      },
    ],
    options: [
      { text: "Intructor", value: "Instructor"},
      { text: "Student", value: "Student"},
      { text: "Assistant", value: "Assistant"},
    ],
  }),
  // watch: {
  //   input(value) {
  //     this.input = value.toUpperCase();
  //   },
  // },
  computed: {
    inputUpperCase() {
      console.log("computed")
      return this.input.toUpperCase();
    },
  },
  methods: {
    addNewUser() {
      this.userList.push(this.newUser);
      this.newUser = { name: "", role: "" };
    },
  },
});
</script>

<style scoped></style>
