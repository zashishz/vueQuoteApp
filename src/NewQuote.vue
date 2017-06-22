<template>
    <div class="row">
        <form action="">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                <label for="quote">Quote</label>
                <textarea class="form-control" name="quote" id="quote" rows="3" v-model="newQuote"></textarea>
            </div>
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    data:function() {
        return {
            newQuote: ""
        }
    },
    methods: {
        createNew() {
            this.$emit('newQuoteAdded', this.newQuote);
            //clear the text area once submitted
            this.newQuote = "";
        }
    }
}
</script>

<style>

</style>
