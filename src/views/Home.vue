<template>
<div class="home container">
    <div class="row">
        <section class="col-lg-2">Thèmes</section>
        <ThreadList class="col-lg-4"></ThreadList>
        <section class="col-lg-6">Commentaires</section>
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

    export default {
        name: 'home',
        components: {
            ThreadList
        }
    }
</script>


<style scoped>
    footer {
    }
    
</style>