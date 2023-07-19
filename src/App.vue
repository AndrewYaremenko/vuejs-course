<template>
    <div>
        <div>
            <button v-on:click="addLike">Like</button>
            <button v-on:click="addDislike">Dislike</button>
        </div>
        <div>Likes: <strong>{{ likes }}</strong></div>
        <div>Dislikes: <strong>{{ dislikes }}</strong></div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            likes: 5,
            dislikes: 2,
        }
    },
    methods: {
        addLike() {
            this.likes++;
        },
        addDislike() {
            this.dislikes++
        }
    }
}
</script>

<style></style>