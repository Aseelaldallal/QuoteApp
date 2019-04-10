<template>
    <div class="container">
        <h5>Quote</h5>
        <textarea cols="30" rows="10" v-model="quote"></textarea>
        <button @click="addQuote" class="btn btn-primary"> Add Quote </button>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                quote: 'Quack'
            }
        }, 
        methods: {
            addQuote() {
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style scoped>

</style>
