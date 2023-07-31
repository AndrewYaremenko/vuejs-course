<template>
  <div class="container">
    <h1>Posts page</h1>
    <input type="text" v-model.number="modificatorValue">
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

export default {
  components: {
    PostList,
    PostForm,
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          title: "Lorem, ipsum.",
          description:
            "Lorem ipsum dolor sit, amet consectetur adipisicing elit.",
        },
        {
          id: 2,
          title: "Lorem ipsum dolor sit amet.",
          description:
            "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Autem, quia?",
        },
        {
          id: 3,
          title: "Lorem, ipsum dolor.",
          description: "Lorem ipsum dolor sit amet consectetur adipisicing.",
        },
      ],
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