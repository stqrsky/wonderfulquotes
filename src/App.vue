<template>
    <div class="container">
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes"></app-quote-grid>     <!-- add property :quote="quotes" (v-bind) expecting props in QuoteGrid.vue passing array in it -->
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to Delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';

    export default {
        data: function() {
            return {
                quotes: [
                    'This is an example Quote.'
                ],
                maxQuotes: 10                       // track the max number of Quotes
            }
        },
        methods: {
            newQuote(quote) {                       // fetch or access the quote from the returned Object of NewQuote.vue / the $event
                this.quotes.push(quote);            // how to use the quote
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote
        }
    }
</script>

<style>

</style>
