<template>
    <div>
        <div class="post" v-for="post in posts">
            <div><strong>Title: </strong> {{post.title}}</div>
            <div><strong>Description: </strong> {{post.description}}</div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            posts: [
                {id: 1, title: "Lorem, ipsum.", description: "Lorem ipsum dolor sit, amet consectetur adipisicing elit."},
                {id: 2, title: "Lorem ipsum dolor sit amet.", description: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Autem, quia?"},
                {id: 3, title: "Lorem, ipsum dolor.", description: "Lorem ipsum dolor sit amet consectetur adipisicing."},
            ]
        }
    },
    methods: {

    }
}
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.post {
    padding: 15px;
    margin-top: 15px;
    border: 3px solid darkgreen;
}
</style>