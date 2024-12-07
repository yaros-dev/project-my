<template>
  <div class="app">
    <PostForm @create="createPost" />
    <PostList :posts="data" />
  </div>
</template>

<script>
import PostForm from "./components/PostForm.vue";
import PostList from "./components/PostList.vue";

export default {
  components: {
    PostForm,
    PostList,
  },
  data() {
    return {
      data: [
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
        {
          id: 4,
          title: "Jambo",
          body: " ntium quis  tiae por odio et labore et velit aut",
        },
        {
          id: 5,
          title: "Google",
          body: " ntium quis  tiae por odio et labore et velit aut",
        },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.data.push(post);
    },
  },
};
</script>

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
