<template>
  <div v-show="posts.length > 0">
    <h3>Posts list</h3>
    <post-item v-for="post in posts" :post="post" :key="post.id" @click="$emit('remove', post)" />
  </div>

  <div v-show="posts.length == 0" style="color: red;">
    <h2>
      Posts list is empty!
    </h2>
  </div>
</template>

<script>
import PostItem from "@/components/PostItem.vue";
export default {
  components: {
    PostItem,
  },
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
};
</script>

<style scoped>
.post {
  padding: 15px;
  margin-top: 15px;
  border: 3px solid darkgreen;
}
</style>