<template>
    <div class="container">
        <app-quote-grid :quotes="quotes"></app-quote-grid>     <!-- add property :quote="quotes" (v-bind) expecting props in QuoteGrid.vue passing array in it -->
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';

    export default {
        data: function() {
            return {
                quotes: [
                    'This is an example Quote.'
                ],
                maxQuotes: 10 // track the max number of Quotes
            }
        },
        components: {
            appQuoteGrid: QuoteGrid
        }
    }
</script>

<style>

</style>
