<template>
    <div class="root">
        <textarea ref="inputText" class="input-text" :value="text"></textarea>
        <button class="button" @click="addQuote">Add Quote</button>
    </div>

</template>

<script>

import {eventBus} from '../main';
export default {
    
    
    
    data(){
        return {
            size:0
        }
    },
    methods:{
        addQuote: function(){
            this.$emit('addNewQuote', this.$refs.inputText.value);
            this.$refs.inputText.value = '';
            this.size++;
        }
    }
}
</script>

<style scoped>

    .root{
        display: flex;
        align-items: center;
        flex-direction: column;
        margin-top:45px;
        width: 100%;
    }

    .input-text{
        width:50%;
        height: 80px;
        resize: none;
    }
    .button{
        background-color: darkblue;
        font-weight: bold;
        padding: 5px 8px;
        color: white;
        margin-top: 10px;
        border-radius: 5px;
        border: none;
    }

    .button:hover{
        opacity: 0.7;
    }
</style>