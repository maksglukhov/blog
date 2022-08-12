<template>
  <div class="app">
    <MyButton @click="showDialog" style="margin: 15px 0">Create post</MyButton>
    <MyDialog v-model:show="dialogVisible">
      <post-form @create="createPost"> </post-form
    ></MyDialog>

    <post-list :posts="posts" @remove="removePost"></post-list>
  </div>
</template>

<script>
import PostForm from "./components/PostForm.vue";
import PostList from "./components/PostList.vue";
import MyButton from "./components/UI/MyButton.vue";
export default {
  components: {
    PostList,
    PostForm,
    MyButton,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "first post", body: "body of first post" },
        { id: 2, title: "second post", body: "body of second post" },
        { id: 3, title: "third post", body: "body of third post" },
        { id: 4, title: "fourth post", body: "body of fourth post" },
      ],
      dialogVisible: false,
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
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

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: blanchedalmond;
}
.app {
  padding: 20px;
}
</style>
