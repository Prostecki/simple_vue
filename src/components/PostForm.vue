<!-- The syntax includes of using template tag for structurizing html contents -->
<template>
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
        class="btn">
        Create
        </button>
    </form>

</template>

<script>

// Need to export the components in order to use in App.vue
export default {
    
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