<template>
    <div @click="deleteQuote"><slot></slot></div>
</template>

<script>
export default {
    methods: {
        deleteQuote() {
            this.$emit('quoteDeleted');
        }
    }
}
</script>
