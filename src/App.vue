<template>
  <h3>Hello, World!</h3>
  <!-- 3. use the component in the template-->
  <!-- <InputMessage /> -->

  <Counter />
</template>

<script>
// 1. import the component
import InputMessage from "./components/InputMessage.vue";
import Counter from "./components/Counter.vue";
export default {
  //2. declare the component
  components: {
    InputMessage,
    Counter,
  },
};
</script>
