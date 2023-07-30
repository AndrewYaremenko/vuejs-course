<template>
  <form @submit.prevent>
    <h4>Create new post</h4>
    <input v-bind:value="post.title" @input="post.title = $event.target.value" type="text" class="input" name="title"
      placeholder="Title" />
    <input v-bind:value="post.description" @input="post.description = $event.target.value" type="text" class="input"
      name="description" placeholder="Description" />
    <my-button class="btnCreate" @click="createPost">Create</my-button>
  </form>
</template>

<script>
import MyButton from "@/components/UI/MyButton";
export default {
  components: {
    MyButton
  },
  data() {
    return {
      post: {
        title: '',
        description: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post);
      this.post = {
        title: '',
        description: '',
      }
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  border: 1px solid darkgreen;
  padding: 15px;
  margin-top: 15px;
}

.btnCreate {
  align-self: flex-end;
}
</style>