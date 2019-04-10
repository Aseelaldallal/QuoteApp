<template>
    <div class="container">
        <app-quotes-adder @quoteAdded="addQuote($event)"></app-quotes-adder>
        <div> 
            <app-quote v-for="(quote,i) in quotes" :key="i">{{quote}}</app-quote>
        </div>
    </div>
</template>

<script>
    import QuotesAdder from './components/QuotesAdder.vue';
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
            }
        },
        components: {
            'app-quotes-adder': QuotesAdder,
            'app-quote': Quote
        },
        
    }
</script>

<style>
</style>
