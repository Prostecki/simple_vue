<template>
    <!-- Iterating over "posts" array and displaying each post -->
    <div class="post">
        <div>
            <div><strong>Title</strong> {{ post.title }} </div>
            <div><strong>Description</strong> {{ post.body }} </div>
        </div>
        <div class="post__btns">
            <MyButton
            @click="$emit('remove', post)"
            >Delete</MyButton>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        post: {
            type: Object,
            requried: true,
        }
    },
}

</script>

<style scoped>
    .post {
        display: flex;
        align-items: center;
        padding: 15px;
        border: 2px solid teal;
        margin-top: 15px;
        justify-content: space-between;
    }
</style>