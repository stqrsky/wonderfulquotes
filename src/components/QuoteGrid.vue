<template>
    <div class="row">
        <app-quote v-for="quote in quotes" :key="quote.id">{{ quote }}</app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';    // the single quote

    export default {
        props: ['quotes'],
        components: {                   // register the single quote
            appQuote: Quote             // assign appQuote as a Selector, then use it in template "<appQuote></appQuote>""
        }
    }
</script>

<style>
    
</style>