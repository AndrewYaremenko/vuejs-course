<template>
  <div class="container">
    <post-form />
    <post-list :posts="posts"/>
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
      title: "",
      description: "",
    };
  },
  methods: {
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        description: this.description,
      };
      this.posts.push(newPost);
      this.title = "";
      this.description = "";
    },
    inputDescription(event) {
      this.description = event.target.value;
    },
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