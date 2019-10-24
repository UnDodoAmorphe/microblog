<template>
<div class="home container">
    <div class="row">
        <ThemeList class="col-lg-2">Thèmes</ThemeList>
        <ThreadList class="col-lg-4" 
            v-model="postTitle">
            </ThreadList>
        <PostAndComments class="col-lg-6" :title="postTitle">
        Commentaires
        </PostAndComments>
    </div>
    <div class="row">
        <footer>
            <p>Je suis le footer</p>
        </footer>
    </div>
</div>
</template>

<script>
    // @ is an alias to /src
    import ThreadList from "@/components/ThreadList.vue"
    import PostAndComments from "@/components/PostAndComments.vue"
    import ThemeList from "@/components/ThemeList.vue"

    export default {
        name: 'home',
        data () {
            return {
                postTitle: null
            }
        },
        components: {
            ThreadList,
            PostAndComments,
            ThemeList
        }
    }
</script>


<style scoped>
    footer {
    }
    
</style>