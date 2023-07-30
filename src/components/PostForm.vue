<template>
  <form @submit.prevent>
    <h4>Create new post</h4>
    <my-input v-bind:value="post.title" @input="post.title = $event.target.value" type="text" class="input" name="title"
      placeholder="Title" />
    <my-input v-bind:value="post.description" @input="post.description = $event.target.value" type="text" class="input"
      name="description" placeholder="Description" />
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