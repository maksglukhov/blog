<template>
  <form @submit.prevent>
    <MyHeader4>Create post</MyHeader4>
    <MyInput v-model="post.title" placeholder="Title" />
    <MyInput v-model="post.body" placeholder="Body" />

    <MyButton @click="createPost" style="align-self: flex-end; margin-top: 15px"
      >Add post</MyButton
    >
  </form>
</template>

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
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}
</style>
