<template>
    <div class="root">
        <h2 >Quotes Added</h2>
        <div class="background-bar">
            <div class="front-bar" :style="{width: (quotes*10)+'%'}">
                <p class="text">{{quotes}}/10</p>
            </div>
        </div>
    </div>
</template>

<script>
import {eventBus} from '../main';
export default {
    props: ['quotes']
}
</script>

<style scoped>
    .root{
        display: flex;
        align-items: center;
        justify-content: space-between;
        flex-direction: column;
        margin-top: 100px;
        width: 80%;
    }

    .front-bar{
        
        background-color: darkblue;
        height: 25px;
        text-align: center;
        transition: width 0.4s ease-in-out;
    }

    .text{
        color: #fff;
        font-weight: bold;
    }

    .root h2{
        align-self: flex-start;
    }

    .background-bar{
        width:100%;
        height: 25px;
        background-color: darkgray;
    }
</style>