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

<template>
  <form class="myform" @submit.prevent>
    <h4>Creating a post</h4>
    <div class="fieds">
      <input
        v-model="post.title"
        class="input"
        type="text"
        placeholder="Title"
      />
      <input
        v-model="post.body"
        class="input"
        type="text"
        placeholder="Description"
      />
      <Button @click="createPost" class="input">Create</Button>
    </div>
  </form>
</template>

<style scoped>
.myform {
  margin-bottom: 20px;
  font-size: 20px;
  max-width: 500px;
}
.fieds {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 8px;
}

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
  font-style: italic;
}

h4 {
  padding: 10px;
}

form {
  padding: 12px;
  border: 2px solid #ccc;
  border-radius: 8px;
}
</style>
