<script>
import PostItem from "./PostItem.vue";
export default {
  components: {
    PostItem,
  },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<template>
  <div>
    <h4>Post list</h4>
    <PostItem v-for="post in posts" :post="post" :key="post.id" />
  </div>
</template>

<style scoped>
h4 {
  font-size: 24px;
  margin-bottom: 10px;
}
</style>
