<template>
  The count is: {{ count }} <button @click="count++">+1</button>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
    };
  },
};
</script>
