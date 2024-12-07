<script>
export default {
  name: "Button",
};
</script>

<template>
  <button class="btn"><slot></slot></button>
</template>

<style scoped>
.btn {
  background: #c1c4e0;
  border: none;
  padding: 4px;
  border-radius: 4px;
}
</style>
