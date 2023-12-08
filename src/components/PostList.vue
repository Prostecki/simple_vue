<!-- The syntax includes of using template tag for structurizing html contents -->
<template>
    <!-- Iterating over 'posts' array and displaying each post -->
    <div class="post" v-for="post in posts">
        <div><strong>Title:</strong> {{ post.title }}</div>
        <div><strong>Description:</strong> {{ post.body }}</div>
    </div>
</template>

<script>

// Need to export the components in order to use in App.vue
export default {

}

</script>

<!-- Styles is using only for this component -->
<style scoped>
.post {
        padding: 15px;
        border: 2px solid teal;
        margin-top: 15px;

    }
</style>