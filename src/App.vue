<script>
import axios from "axios";
import PostForm from "./components/PostForm.vue";
import PostList from "./components/PostList.vue";
import Dialog from "./components/UI/Dialog.vue";

export default {
  components: {
    PostForm,
    PostList,
  },
  data() {
    return {
      posts: [],
      dialogVisible: false,
      loading: false,
    };
  },
  methods: {
    createPost(post) {
      if (!post.title || !post.body) {
        return;
      }

      this.posts.unshift(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter((p) => p.id !== post.id);
    },
    showDialog() {
      this.dialogVisible = true;
    },
    async fetchPosts() {
      try {
        this.loading = true;
        const response = await axios.get(
          "https://jsonplaceholder.typicode.com/posts?_limit=10"
        );
        this.posts = response.data;
      } catch (error) {
        alert("Error", error);
      } finally {
        this.loading = false;
      }
    },
  },
  mounted() {
    this.fetchPosts();
  },
};
</script>

<template>
  <div class="app">
    <Button @click="showDialog">Create new post</Button>
    <Dialog v-model:show="dialogVisible">
      <PostForm @create="createPost" />
    </Dialog>
    <PostList :posts="posts" @remove="removePost" v-if="!loading" />
    <div v-else class="spinner"><Spinner /></div>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}

.spinner {
  margin: 0 auto;
  max-width: 100px;
  height: 100px;
}
</style>
