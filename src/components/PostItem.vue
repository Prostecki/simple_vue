<template>
    <!-- Iterating over "posts" array and displaying each post -->
    <div class="post">
        <div>
            <div><strong>Title</strong> {{ post.title }} </div>
            <div><strong>Description</strong> {{ post.body }} </div>
        </div>
        <div class="post__btns">
            <button>Delete</button>
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
        }
    }

</script>

<style scoped>
    .post {
        display: flex;
        align-items: center;
        padding: 15px;
        border: 2px solid teal;
        margin-top: 15px;
        box-shadow: inset 1px 1px 5px black;
        justify-content: space-between;
    }
</style>