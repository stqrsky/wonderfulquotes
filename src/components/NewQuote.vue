<template>
    <div class="row">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-sx-12 col-md-6 col-md-offset-3 form-group">
                <label>Write Your Quote here:</label>
                <textarea class="form-control" rows="3" v-model="quote"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-sx-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>   <!-- .prevent = don't submit the form, don't send request to the server to reload the page / prevent the default behavior -->
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        data: function() {
            return {
                quote: ''        // binding with the textarea / gets set when we enter something in textarea
            };
        },
        methods: {
            createNew() {
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style>
    
</style>