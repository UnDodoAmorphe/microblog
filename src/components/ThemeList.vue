<template>
<section id="themeList">
    <label>
        Filtres
    </label>
    <ul class="list-group">
        <li v-for="theme in list" v-bind:key="theme.id" class="list-group-item">
            {{theme.name}}
        </li>
    </ul>
    <button class="btn btn-lg"><span class="glyphicon glyphicon-plus-sign"></span></button>
</section> 
</template>

<script>
    const axios = require('axios').default;
    export default {
        name: "ThemeList",
        data () {
            return {
                list: []
            }
        },
        mounted () {
          axios.get('https://localhost:5001/api/thread/')
            .then(response => (this.list = response.data))
        },
        components: {
        }
    }
</script>

<style>
    
</style>