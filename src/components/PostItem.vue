<template>
  <div class="post">
    <div>
      <div><strong>Title: </strong>{{ post.title }}</div>
      <div><strong>Description: </strong>{{ post.description }}</div>
    </div>
    <div class="post__btns">
      <my-button>Delete</my-button>
    </div>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton";
export default {
  components: {
    MyButton,
  },
  props: {
    post: {
      type: Object,
      required: true,
    }
  }

};
</script>

<style scoped>
.post {
  padding: 15px;
  margin-top: 15px;
  border: 3px solid darkgreen;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>