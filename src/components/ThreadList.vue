<template>
<section id="threadList">
    <label>
        NOM DU CHANNEL
    </label>
    <button class="btn btn-lg btn-block" @click="isEnabled = !isEnabled">
        Commencer un nouveau thread
    </button>
    <input type="text" v-show="isEnabled" placeholder="Choisissez un titre">

<ul id="list" class="list-group">
    <li v-for="item in info" v-bind:key="item.id" class="list-group-item">
        {{item.title}}
    </li>
</ul>
</section>
</template>

<script>
    const axios = require('axios').default;
    export default {
        name: "ThreadList",
        data () {
            return {
                items: [
                    {title: "Foo",
                     body: "Lorem ipsum etc"},
                    {title: "Bar",
                     body: "Ipsum lorem etc"}
                ],
                isEnabled: false,
                info: null
            }
        },
        methods: {
            /*content: function () {
               axios.get("https://localhost:5001/api/thread/")
                .then(function(response) {
                      
                      })
                .catch(function(response) {
                   
               });
            return response.data;
            }*/
        },
        mounted() {
             axios.get('https://localhost:5001/api/thread/')
      .then(response => (this.info = response.data))
        },
        
        components: {
        }
    }
</script>

<style scoped>
    li {
        margin-top: 5px;
    }
</style>