<template>
    <div class="container">
        <app-quote-tracker :numQuotes="quotes.length" :maxQuotes="maxQuotes"></app-quote-tracker>
        <app-quotes-adder @quoteAdded="addQuote($event)"></app-quotes-adder>
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote($event)"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Click Quote to Delete</div>
            </div>
        </div>
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
                if(this.quotes.length < this.maxQuotes) {
                    this.quotes.push(quote);
                } else {
                    return alert('Please delete quotes first');
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
