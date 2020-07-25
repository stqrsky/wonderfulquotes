<template>
    <div class="container">
        <app-header></app-header>
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>     <!-- add property :quote="quotes" (v-bind) expecting props in QuoteGrid.vue passing array in it -->
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
    import Header from './components/Header.vue';

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
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);       // access quotes Array, start splicing at position of index, then splice one element / modify existing array and removing one element
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: AppHeader
        }
    }
</script>

<style>

</style>
