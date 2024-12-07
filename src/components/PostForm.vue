<template>
  <form class="myform" @submit.prevent>
    <h4>Створення поста</h4>
    <input v-model="post.title" class="input" type="text" placeholder="Title" />
    <input
      v-model="post.body"
      class="input"
      type="text"
      placeholder="Description"
    />
    <button @click="createPost" class="input">Create</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = self.crypto.randomUUID();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style scoped>
.myform {
  margin-bottom: 20px;
  font-size: 20px;
}

.input {
  width: 100%;
  max-width: 200px;
  padding: 10px 15px;
  font-size: 16px;
  font-family: Arial, sans-serif;
  color: #333;
  background-color: #f9f9f9;
  border: 1px solid #ccc;
  border-radius: 4px;
  outline: none;
  transition: border-color 0.3s, box-shadow 0.3s;
  margin: 0 8px;
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
  font-style: italic;
}

h4 {
  padding: 20px;
}

form {
  padding: 10px;
  border: 2px solid rgb(84, 4, 4);
  border-radius: 8px;
}
</style>
