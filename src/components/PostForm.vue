<!-- The syntax includes using template tags for structuring HTML contents -->
<template>
    <!-- The form with a submit event listener that prevents the default behavior -->
    <form @submit.prevent>

        <h4>Create a post</h4>

        <!-- Input field for the title, with two-way binding to the 'title' property in the data -->
        <input
        v-model="post.title"
        class="input" 
        type="text"
        placeholder="Title">

        <!-- Input field for the body with two-way binding to the 'body' property in the data -->
        <input 
        v-model="post.body"
        class="input" 
        type="text" 
        placeholder="Description">
        
        <!-- Button for creating a post, with a click event listener calling the 'createPost' method -->
        <button 
        class="btn"
        @click="createPost">
        Create
        </button>
    </form>
</template>

<script>
// Need to export the component in order to use in App.vue
export default {
    data() {
        return {
            // Data property 'post' with title and body properties
            post: {
                title: '', // Title property for the post
                body: '',  // Body property for the post
            }
        }
    },
    methods: {
        // Method for creating a post
        createPost() {
            // Assign a unique id (timestamp) to the post
            this.post.id = Date.now();
            
            // Emit a custom event 'create' with the post data
            this.$emit('create', this.post)

            // Reset the post data for a new post
            this.post = {
                title: '',
                body: '',
            }
        }
    }
}
</script>

<!-- Styles specific to this component, scoped to avoid global style conflicts -->
<style scoped>
    form {
        display: flex;
        flex-direction: column;
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
