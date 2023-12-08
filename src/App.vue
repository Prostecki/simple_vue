<template>
    <div class="app">
        <!-- submit prevent - -->
        <form @submit.prevent>
            <h4>Create a post</h4>
            <input @input="title = $event.target.value" v-bind:value="title" class="input" type="text" placeholder="Title">
            <input @input="body = $event.target.value" v-bind:value="body" class="input" type="text" placeholder="Description">
            <button class="btn" @click="createPost">Create</button>
        </form>
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
            posts: [
                {id: 1, title: 'Vuejs', body: 'Description of post 1'},
                {id: 2, title: 'Vuejs', body: 'Description of post 2'},
                {id: 3, title: 'Vuejs', body: 'Description of post 3'},
                {id: 4, title: 'Vuejs', body: 'Description of post 4'}
            ],
            title: '',
            body: '',
        }
    },
    methods: {
        createPost() {
            const newPost = {
                id: Date.now(),
                title: this.title,
                body: this.body,
            }
            this.posts.push(newPost);
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