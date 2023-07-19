<template>
    <div class="container">
        <form @submit.prevent>
            <h4>Create new post</h4>
            <input v-bind:value="title" @input="title = $event.target.value" type="text" class="input" name="title"
                placeholder="Title">
            <input v-bind:value="description" @input="inputDescription" type="text" class="input" name="description"
                placeholder="Description">
            <button class="btn" @click="createPost">Create</button>
        </form>
        <div class="post" v-for="post in posts">
            <div><strong>Title: </strong> {{ post.title }}</div>
            <div><strong>Description: </strong> {{ post.description }}</div>

        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            posts: [
                { id: 1, title: "Lorem, ipsum.", description: "Lorem ipsum dolor sit, amet consectetur adipisicing elit." },
                { id: 2, title: "Lorem ipsum dolor sit amet.", description: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Autem, quia?" },
                { id: 3, title: "Lorem, ipsum dolor.", description: "Lorem ipsum dolor sit amet consectetur adipisicing." },
            ],
            title: '',
            description: '',
        }
    },
    methods: {
        createPost() {
            const newPost = {
                id: Date.now(),
                title: this.title,
                description: this.description,
            }
            this.posts.push(newPost);
            this.title = '';
            this.description= '';
        },
        inputDescription(event) {
            this.description = event.target.value;
        }
    }
}
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

.post {
    padding: 15px;
    margin-top: 15px;
    border: 3px solid darkgreen;
}

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