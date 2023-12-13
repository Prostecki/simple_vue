<!-- The syntax includes of using template tag for structurizing html contents -->
<template>
    <div class="app">
        <h1>Page with posts</h1>
        <MyButton
        @click="showDialog"
        >Create a user</MyButton>
        <MyDialog v-model:show="dialogVisible">
            <PostForm
            @create="createPost" 
            />
        </MyDialog>
        <PostList 
        v-bind:posts="posts"
        @remove="removePost"
        />
    </div>
</template>

<script>

// Need to add .vue for displaying components!
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";
import MyDialog from "@/components/UI/MyDialog.vue";

// Need to export default components in order to use all of them wherever
export default {
    components: {
        PostList, 
        PostForm,
        MyDialog
    },
    data() {
        return {
            // Initial array of posts
            posts: [
                {id: 1, title: 'Vuejs', body: 'Description of post 1'},
                {id: 2, title: 'Vuejs', body: 'Description of post 2'},
                {id: 3, title: 'Vuejs', body: 'Description of post 3'},
                {id: 4, title: 'Vuejs', body: 'Description of post 4'}
            ],
            dialogVisible: false
        }
    },
    methods: {
        // Method to create a new post
        createPost(post){
            this.posts.push(post);
        },
        removePost(post) {
            this.posts = this.posts.filter(p => p.id !== post.id);
        },
        showDialog() {
            this.dialogVisible = true;
        }
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