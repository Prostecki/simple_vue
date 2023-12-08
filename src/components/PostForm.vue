<!-- The syntax includes of using template tag for structurizing html contents -->
<template>
    <!-- The form with a submit event listener that prevents the default behavior -->
    <form @submit.prevent>

        <h4>Create a post</h4>

        <!-- Input field for the title, with two-way binding to the 'title' property in the data -->
        <input 
        @input="post.title = $event.target.value" 
        v-bind:value="post.title" 
        class="input" 
        type="text" 
        placeholder="Title">

        <!-- Input field for the body, with two-way binding to the 'body' property in the data -->
        <input 
        @input="post.body = $event.target.value" 
        v-bind:value="post.body" 
        class="input" 
        type="text" 
        placeholder="Description">

        <button 
        class="btn">
        Create
        </button>
    </form>

</template>

<script>

// Need to export the components in order to use in App.vue
export default {
    data() {
        return {
            post: {
                // Title property for the post
                title: '',
                // Body property for the post
                body: '',
            }
        }
    }
}

</script>

<!-- Styles is using only for this component -->
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