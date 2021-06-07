<template>
  <h2>Users</h2>
  <User v-for="user in users" :key="user.id" :user="user" />
</template>
<script>
import axios from "axios";
import { defineAsyncComponent, ref } from "vue";
// import User from "./User";
const User = defineAsyncComponent(() => import("./User"));
export default {
  components: {
    User,
  },
  async setup() {
    const users = ref(null);
    const url = "https://jsonplaceholder.typicode.com/users";
    await axios.get(url).then((response) => {
      users.value = response.data;
    });

    return { users };
  },
};
</script>