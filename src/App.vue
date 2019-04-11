<template>
    <div class="container">
        <app-quote-tracker :numQuotes="quotes.length"></app-quote-tracker>
        <app-quotes-adder @quoteAdded="addQuote($event)"></app-quotes-adder>
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote($event)"></app-quote-grid>
    </div>
</template>

<script>
    import QuotesAdder from './components/QuotesAdder.vue';
    import QuoteGrid from './components/QuotesGrid.vue'
    import QuoteTracker from './components/QuoteTracker.vue';
    export default {
        data() {
            return {
                maxQuotes: 10,
                quotes:[]
            }
        }, 
        methods: {
            addQuote(quote) {
                if(quotes.length < maxQuotes) {
                    this.quotes.push(quote);
                }
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        },
        components: {
            'app-quotes-adder': QuotesAdder,
            'app-quote-tracker': QuoteTracker,
            'app-quote-grid': QuoteGrid
        },
        
    }
</script>

<style>
</style>
