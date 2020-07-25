<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" :key="quote.id" @click.native="deleteQuote(index)">{{ quote }}</app-quote>      <!--  .native modifier (deletion of quote) -->
    </div>
</template>

<script>
    import Quote from './Quote.vue';    // the single quote

    export default {
        props: ['quotes'],
        components: {                   // register the single quote
            appQuote: Quote             // assign appQuote as a Selector, then use it in template "<appQuote></appQuote>""
        },
        methods: {
            deleteQuote(index) {             // add the second Argument "current index" in v-for, pass index in @click deleteQuote(index), and in method.
                this.$emit('quoteDeleted', index);
            }
        }
    }
</script>

<style>
    
</style>