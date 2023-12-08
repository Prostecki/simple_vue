<!-- The syntax includes of using template tag for structurizing html contents -->
<template>
    <div class="app">
        <PostForm 
        @create="createPost"
        />
        <PostList 
        v-bind:posts="posts" 
        />
    </div>
</template>

<script>

// Need to add .vue for displaying components!
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";

// Need to export default components in order to use all of them wherever
export default {
    components: {
        PostList, 
        PostForm
    },
    data() {
        return {
            // Initial array of posts
            posts: [
                {id: 1, title: 'Vuejs', body: 'Description of post 1'},
                {id: 2, title: 'Vuejs', body: 'Description of post 2'},
                {id: 3, title: 'Vuejs', body: 'Description of post 3'},
                {id: 4, title: 'Vuejs', body: 'Description of post 4'}
            ]
        }
    },
    methods: {
        // Method to create a new post
        createPost(post){
            this.posts.push(post);
        },
    }
}
</script>

<!-- Styles is using only for this component -->
<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    .app {
        padding: 20px;
    }
    
</style>