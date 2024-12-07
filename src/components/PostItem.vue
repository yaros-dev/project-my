<template>
  <div class="post">
    <div>
      <div>
        Title:<strong>{{ post.title }}</strong>
      </div>
      <div>
        Decription:<strong>{{ post.body }}</strong>
      </div>
      <div class="btn-posts">
        <button class="btn">Delete❌</button>
        <button class="btn">Edit🟨</button>
      </div>
    </div>
  </div>
</template>

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

<style scoped>
.post {
  border: 2px solid blueviolet;
  margin-bottom: 3px;
  padding: 5px;
  max-width: 500px;
  transition: all 0.1s;
}

.post:hover {
  border: 2px solid rgb(13, 245, 13);
}

.btn-posts {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  gap: 8px;
}

.btn {
  background: #c1c4e0;
  border: none;
  padding: 4px;
  border-radius: 4px;
}
</style>
