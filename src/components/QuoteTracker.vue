<template>
    <div>
        <h1>Quotes Added</h1>
        <div class="progressBar">
            <div class="progress">
                {{numQuotes}}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        numQuotes: {
            type: Number,
            required: true
        }
    }
    
}
</script>

<style scoped>

</style>
