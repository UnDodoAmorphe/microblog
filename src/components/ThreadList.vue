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
    <li v-for="item in items" v-bind:key="item.id" @click="content" class="list-group-item">
        {{item.title}}
    </li>
</ul>
</section>
</template>

<script>
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
                isEnabled: false
            }
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