<script>
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
      posts: [
        {
          id: 1,
          title: "javaScript",
          body: "quia et suscipit\nsuscipit ",
        },
        {
          id: 2,
          title: "Pascal",
          body: "est rerum t  neque nisi nulla",
        },
        {
          id: 3,
          title: "Java",
          body: " ntium quis  tiae por odio et labore et velit aut",
        },
      ],
      dialogVisible: false,
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
  },
};
</script>

<template>
  <div class="app">
    <Button @click="showDialog">Create new post</Button>
    <Dialog v-model:show="dialogVisible">
      <PostForm @create="createPost" />
    </Dialog>
    <PostList :posts="posts" @remove="removePost" />
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
</style>
