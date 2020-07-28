<template>
    <div class="root">
        <appQuote v-for="(t,i) in text" :key="i" @click.native="removeIten(i)" style="cursor: pointer;"><p>{{t}}</p></appQuote>
    </div>
</template>

<script>
    import Quote from './Quote.vue'; 
    export default {
        props: ['text'],
        components: {
            appQuote: Quote
        },
        methods:{
            removeIten: function(e){
                this.$emit('quoteDeleted', e);
            }
        }
    }
</script>

<style scoped>
    .root{
        display: flex;
        align-items: center;
        width: 100%;
        flex-wrap: wrap;
        margin-top: 15px;
    }
</style>