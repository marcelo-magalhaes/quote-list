<template>
    <div class="container">
        <appHeader :quotes="text.length">
        </appHeader>
        <app-input @addNewQuote="addQuote"></app-input>
        <appQuotes :text="text" @quoteDeleted="deleteQuote">
        </appQuotes>
        <div class="footer">
            <p>To delete a quote, just click!</p>
        </div>
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
                if(this.text.length<10&&quote.length!=0)
                    this.text.push(quote);
                else if(quote.length==0)
                    alert("You can't add a empty quote!");
                else
                    alert("Delete a quote first!")
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

    .footer{
        display: flex;
        align-items: center;
        width: 100%;
        background-color: rgba(14, 185, 185,0.5);
        text-align: center;
        justify-content: center;
        color: rgb(0, 53, 133);
        height: 50px;
        font-weight: bold;
    }
</style>
