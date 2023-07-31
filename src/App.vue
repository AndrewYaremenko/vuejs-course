<template>
  <div class="container">
    <h1>Posts page</h1>
    <my-button @click="fetchPosts" style="margin-right: 10px;">Get posts</my-button>
    <my-button @click="showDialog" style="margin-bottom: 25px;">Create post</my-button>
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost" />
    </my-dialog>

    <post-list :posts="posts" @remove="removePost" />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
import axios from "axios";

export default {
  components: {
    PostList,
    PostForm,
  },
  data() {
    return {
      posts: [],
      dialogVisible: false,
      modificatorValue: "",
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id);
    },
    showDialog() {
      this.dialogVisible = true;
    },
    async fetchPosts() {
      try {
        const responce = await axios.get("https://jsonplaceholder.typicode.com/posts?_limit=10");
        this.posts = responce.data;
      } catch (e) {
        alert('Error');
      }
    }
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  margin: 30px;
}
</style>