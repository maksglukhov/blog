<template>
  <div v-if="posts.length > 0">
    <div>
      <MyHeader4>List of posts</MyHeader4>
      <MyHeader4> quantity: {{ posts.length }}</MyHeader4>
    </div>

    <post-item
      :post="post"
      v-for="post in posts"
      :key="post.id"
      @remove="$emit('remove', post)"
    ></post-item>
  </div>
  <MyHeader4 v-else style="color: brown"> There is no posts</MyHeader4>
</template>

<script>
import PostItem from "./PostItem.vue";
export default {
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
  components: { PostItem },
};
</script>

<style scoped></style>
