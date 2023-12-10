<!-- The syntax includes of using template tag for structurizing html contents -->
<template>
    <!-- Iterating over posts array and displaying each post -->
    <div>
        <h3>Users list</h3>
        <PostItem 
        v-for="post in posts"
        :post="post" />
    </div>
</template>

<script>
import PostItem from "@/components/PostItem.vue"
// Need to export the components in order to use in App.vue
export default {
    components: {PostItem},
    props: {
        posts: {
            type: Array,
            required: true
        }
    }
}

</script>

<!-- Styles is using only for this component -->
<style scoped>

</style>