<template>
    <div class="container">
        <app-header :quotesCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
        <add-new-quote @newQuoteAdded="addNewQuote"></add-new-quote>
        <quotes-grid :quotes="quotes" @quoteDeleted="deleteQuote"></quotes-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on the Quote to delete!</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuotesGrid from './QuotesGrid.vue';
    import NewQuote from './NewQuote.vue';
    import Header from './Header.vue';
    export default {
        data:function() {
            return {
                maxQuotes: 10,
                quotes: ['Initial Quote Just a Placeholder']
            }
        },
        methods: {
            addNewQuote(data) {
                if(this.quotes.length >=  this.maxQuotes) {
                    return alert("Please Delete Quotes - Max Limit Reached!!!")
                }
                this.quotes.push(data);
            },
            deleteQuote(index) {
                this.quotes.splice(index,1);
            }
        },
        components: {
            quotesGrid: QuotesGrid,
            addNewQuote: NewQuote,
            appHeader: Header
        }
    }
</script>

<style>

</style>
