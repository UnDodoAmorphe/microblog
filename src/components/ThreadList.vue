<template>
<section id="threadList">
    <label>
        NOM DU CHANNEL
    </label>
    <button class="btn btn-lg btn-block" @click="isEnabled = !isEnabled">
        Commencer un nouveau thread
    </button>
    <input type="text" 
           :value="value" 
           v-show="isEnabled" 
           placeholder="Choisissez un titre" @keyup.enter="$emit('input', $event.target.value)"
           class="form-control">

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
                isEnabled: false,
                info: []
            }
        },
        props: [
            "value"
        ],
        methods: {

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