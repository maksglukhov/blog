<template>
  <div class="post">
    <div>
      <div><strong>Title: </strong>{{ post.title }}</div>
      <div><strong>Body: </strong>{{ post.body }}</div>
    </div>
    <MyButton style="color: brown" @click="$emit('remove', post)"
      >Delete</MyButton
    >
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.post {
  padding: 15px;
  border: 2px solid teal;
  border-radius: 20px;
  margin-top: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
