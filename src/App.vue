<template>
  <div class="container">
    <post-form @create="createPost" />
    <post-list :posts="posts" @remove="removePost"/>
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
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
    removePost(post){
      this.posts = this.posts.filter(p => p.id !== post.id);
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