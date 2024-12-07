<script>
export default {
  name: "Input",
  props: {
    modelValue: [String, Number],
  },
  methods: {
    updateInput(event) {
      this.$emit("update:modelValue", event.target.value);
    },
  },
};
</script>

<template>
  <input class="input" :value="modelValue" @input="updateInput" />
</template>

<style>
.input {
  width: 100%;
  max-width: 150px;
  padding: 5px 7px;
  font-size: 16px;
  font-family: Arial, sans-serif;
  color: #333;
  background-color: #f9f9f9;
  border: 1px solid #ccc;
  border-radius: 4px;
  outline: none;
  transition: border-color 0.3s, box-shadow 0.3s;
}

.input:focus {
  border-color: #007bff;
  box-shadow: 0 0 5px rgba(0, 123, 255, 0.5);
}

.input:hover {
  border-color: #999;
}

.input:disabled {
  background-color: #e9ecef;
  color: #6c757d;
  cursor: not-allowed;
}

input::placeholder {
  color: #aaa;
}
</style>
