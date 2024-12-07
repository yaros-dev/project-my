<script>
export default {
  props: {
    post: { type: Object, required: true },
  },
  methods: {
    deletePost(id) {},
  },
};
</script>

<template>
  <div class="post">
    <div class="inner-post">
      <div class="title">
        Title:<strong>{{ post.title }}</strong>
      </div>
      <div class="decription">
        Decription:<strong>{{ post.body }}</strong>
      </div>
      <div class="btn-posts">
        <Button>Delete</Button>
        <Button>Edit</Button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.post {
  color: #333;
  background-color: #f9f9f9;
  border: 1px solid #ccc;
  border-radius: 4px;
  outline: none;
  margin-bottom: 8px;
  padding: 5px;
  max-width: 500px;
  transition: all 0.1s;
}
.inner-post {
  padding: 10px;
}

.title {
  margin-bottom: 4px;
  max-width: 150px;
  white-space: nowrap;
  overflow: hidden;
}

.decription {
  overflow: hidden;
  max-width: 150px;
  white-space: nowrap;
}

.post:hover {
  border: 1px solid rgb(51, 82, 51);
}

.btn-posts {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  gap: 8px;
}
</style>
