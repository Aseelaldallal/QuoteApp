<template>
    <div class="row">
        <app-quote 
            v-for="(quote,i) in quotes" 
            :key="i"
            @quoteDeleted="deleteQuote(i)">
            {{quote}}
        </app-quote>
    </div>
</template>

<script>
import Quote from './Quote.vue';
export default {
    props: ['quotes'],
    methods: {
        deleteQuote(index) {
            this.$emit('quoteDeleted', index);
        }
    },
    components: {
        'app-quote': Quote
    }
}
</script>

