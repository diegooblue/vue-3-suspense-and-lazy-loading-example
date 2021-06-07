<template>
  <HelloWorld msg="Suspense and Lazy Loading Example" />
  <div v-if="errMsg">{{ errMsg }}</div>
  <Suspense v-else>
    <template #default>
      <Users />
    </template>
    <template #fallback>
      <div>Loading...</div>
    </template>
  </Suspense>
</template>

<script>
import HelloWorld from "./HelloWorld";
import Users from "./Users";
import { onErrorCaptured, ref } from "vue";
export default {
  components: {
    HelloWorld,
    Users,
  },
  setup() {
    const errMsg = ref(null);
    onErrorCaptured((error) => {
      errMsg.value = error.message;
    });
    return {
      errMsg,
    };
  },
};
</script>
