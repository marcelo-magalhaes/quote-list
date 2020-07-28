<template>
    <div class="container">
        <appHeader :quotes="text.length">
        </appHeader>
        <app-input @addNewQuote="addQuote"></app-input>
        <appQuotes :text="text" @quoteDeleted="deleteQuote">
        </appQuotes>

    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import InputArea from './components/inputQuote.vue';
    import QuoteArea from './components/Quotes.vue';
    
    import {eventBus} from './main';

    export default {
        data(){
            return {
                text: []
         }
        },
        components:{
            appHeader: Header,
            appInput: InputArea,
            appQuotes: QuoteArea,
        },
        methods:{
            addQuote(quote){
                this.text.push(quote);
            },
            deleteQuote(index){
                this.text.splice(index,1);
            }
        }
    }
</script>

<style>
    .container{
        display: flex;
        align-items: center;
        flex-direction: column;
        width: 100%;
    }
</style>
