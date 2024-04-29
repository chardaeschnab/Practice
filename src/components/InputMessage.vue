<template>
<div>The message is: {{ message }}</div>

<input v-model="message"/> 
</template>

<script>
export default {
  data() {
    return {
      message: "Barcelona",
    };
  },
};
</script>
