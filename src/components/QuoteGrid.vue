<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{ quote }}</app-quote>
    </div>    
</template>

<script>
    import Quote from './Quote.vue';
    export default {
        props: ['quotes'],
        components: {
            appQuote: Quote
        },

        methods: {
            deleteQuote(index) { //use index to delete elements in array
                this.$emit('quoteDeleted', index); //Custom event to delete quote
            }
        }
    }
</script>

<style>
   
</style>
