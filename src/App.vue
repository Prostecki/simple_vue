<template>
    <div class="app">
        <!-- submit prevent - stops a default behavior of webpage (reload page after submit button)-->
        <form @submit.prevent>

            <h4>Create a post</h4>

            <!-- @input - binding the input value to the 'title' data property -->
            <input 
            @input="title = $event.target.value" 
            v-bind:value="title" 
            class="input" 
            type="text" 
            placeholder="Title">

            <!-- @input - binding the input value to the 'body' data property -->
            <input 
            @input="body = $event.target.value" 
            v-bind:value="body" 
            class="input" 
            type="text" 
            placeholder="Description">

            <button 
            class="btn" 
            @click="createPost">
            Create
            </button>
        </form>

        <!-- Iterating over 'posts' array and displaying each post -->
        <div class="post" v-for="post in posts">
            <div><strong>Title:</strong> {{ post.title }}</div>
            <div><strong>Description:</strong> {{ post.body }}</div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            // Initial array of posts
            posts: [
                {id: 1, title: 'Vuejs', body: 'Description of post 1'},
                {id: 2, title: 'Vuejs', body: 'Description of post 2'},
                {id: 3, title: 'Vuejs', body: 'Description of post 3'},
                {id: 4, title: 'Vuejs', body: 'Description of post 4'}
            ],
            // Data properties for form inputs
            title: '',
            body: '',
        }
    },
    methods: {
        // Method to create a new post
        createPost() {
            // Create a new post object
            const newPost = {
                id: Date.now(),
                title: this.title,
                body: this.body,
            }
            // Push the new post to the 'posts' array
            this.posts.push(newPost);
            
            // Clear the form inputs
            this.title = '';
            this.body = '';
        },
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
        border: 2px solid teal;
        margin-top: 15px;

    }
    form {
        display: flex;
        flex-direction: column;

    }
    .app {
        padding: 20px;
    }
    .btn {
        margin-top: 15px;
        align-self: flex-end;
        padding: 10px 15px;
        background: none;
        color: teal;
        border: 1px solid teal;
    }
    .input {
        width: 100%;
        border: 1px solid teal;
        padding: 10px 15px;
        margin-top: 15px;
    }
</style>