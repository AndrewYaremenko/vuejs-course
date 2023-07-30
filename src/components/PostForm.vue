<template>
  <form @submit.prevent>
    <h4>Create new post</h4>
    <my-input v-model="post.title" type="text" name="title" placeholder="Title" />
    <my-input v-model="post.description" type="text" name="description" placeholder="Description" />
    <my-button class="btnCreate" @click="createPost">Create</my-button>
  </form>
</template>

<script>
export default {
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

.btnCreate {
  align-self: flex-end;
}
</style>