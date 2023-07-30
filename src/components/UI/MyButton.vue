<template>
    <button class="btn">
        <slot></slot>
    </button>
</template>
<script>
export default {

}
</script>
<style scoped>
.btn {
    margin-top: 15px;
    padding: 10px 15px;
    color: teal;
    background: none;
    border: 1px solid darkgreen;
}
</style>