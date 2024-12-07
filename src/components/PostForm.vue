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
      <Input v-model="post.title" type="text" placeholder="Title" />
      <Input v-model="post.body" type="text" placeholder="Description" />
      <Button @click="createPost" class="input">Create</Button>
    </div>
  </form>
</template>

<style>
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

h4 {
  padding: 10px;
}

form {
  padding: 12px;
  border: 2px solid #ccc;
  border-radius: 8px;
}
</style>
