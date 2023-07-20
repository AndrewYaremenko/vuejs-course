<template>
  <form @submit.prevent>
    <h4>Create new post</h4>
    <input
      v-bind:value="post.title"
      @input="post.title = $event.target.value"
      type="text"
      class="input"
      name="title"
      placeholder="Title"
    />
    <input
      v-bind:value="post.description"
      @input="post.description = $event.target.value"
      type="text"
      class="input"
      name="description"
      placeholder="Description"
    />
    <button class="btn" @click="createPost">Create</button>
  </form>
</template>

<script>
export default {
    data() {
        return {
            post: {
                title: '',
                description:  '',
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

.btn {
  margin-top: 15px;
  padding: 10px 15px;
  align-self: flex-end;
  color: teal;
  background: none;
  border: 1px solid darkgreen;
}
</style>