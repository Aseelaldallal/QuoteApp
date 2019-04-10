<template>
    <div class="container">
        <app-quote-tracker :numQuotes="quotes.length"></app-quote-tracker>
        <app-quotes-adder @quoteAdded="addQuote($event)"></app-quotes-adder>
        <div> 
            <app-quote 
                v-for="(quote,i) in quotes" 
                :key="i"
                @quoteDeleted="deleteQuote(i)">
                {{quote}}
            </app-quote>
        </div>
    </div>
</template>

<script>
    import QuotesAdder from './components/QuotesAdder.vue';
    import QuoteTracker from './components/QuoteTracker.vue';
    import Quote from './components/Quote.vue';
    export default {
        data() {
            return {
                quotes:[]
            }
        }, 
        methods: {
            addQuote(quote) {
                console.log('Adding quote', quote);
                this.quotes.push(quote);
            },
            deleteQuote(index) {
                console.log('Deleting Quote', index);
                this.quotes.splice(index, 1);
            }
        },
        components: {
            'app-quotes-adder': QuotesAdder,
            'app-quote': Quote,
            'app-quote-tracker': QuoteTracker
        },
        
    }
</script>

<style>
</style>
