<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
        <new-quote @addNewQuote="newQuote"></new-quote>
        <quote-grid :quotes="quotes" @delQuote="dropQuote"></quote-grid>
    </div>
</template>

<script>
    import QouteGrid from "./components/QoutesGrid.vue";
    import NewQoute from "./components/NewQoute.vue";
    import Header from "./components/Headr.vue";
    export default {
        data(){
          return {
              quotes: ['test', 'test2'],
              maxQuotes: 10
          }
        },
        components: {
            "quote-grid": QouteGrid,
            "new-quote": NewQoute,
            "app-header": Header,
        },
        methods:{
            newQuote(quote){
                if(this.quotes.length >= 10){
                    return alert('Delete some quotes, maximum is :' + this.maxQuotes);
                }
                this.quotes.push(quote)
            },
            dropQuote(index){
                this.quotes.splice(this.quotes.indexOf(index),1);
            }
        },


    }
</script>

<style>
</style>
