<template>
<section id="postAndComments">
    <article>
        article
    </article>
    <textarea placeholder="Ecrire un commentaire" class="form-control"
    ></textarea>
    <ul class="list-group">
        <li v-for="comm in post" v-bind:key="comm.id" class="list-group-item">
            {{comm.value}}
        </li>
    </ul>
</section>
</template>

<script>
    const axios = require('axios').default;
    export default {
        name: "PostAndComments",
        props: {
            title: {
                type: String,
                default: ""
            }
        },
        data () {
            return {
                post: []
            }
        },
        mounted () {
          axios.get('https://localhost:5001/api/thread?title=' + this.title)
            .then(response => (this.post = response.data))
        },
        components: {
        }
    }
</script>

<style>
    
</style>