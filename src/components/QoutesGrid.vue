<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{ quote }}</app-quote>
    </div>
</template>
<script>
    import Qoute from "./Qoute.vue";
    export default {
        props: ['quotes'],
        components: {
            "app-quote": Qoute
        },
        methods: {
            deleteQuote(index){
                this.$emit('delQuote', index)
            }
        }
    }
</script>