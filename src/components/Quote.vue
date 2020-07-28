<template>
    <div class="root">
        <slot></slot>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    .root{
        width: 30%;
        border: 2px rgba(174,168,162,0.3) solid;
        margin: 5px 15px;
        text-align: center;
        display: flex;
        align-items: center;
        justify-content: space-around;
    }

    .root:hover{
        background-color: rgba(247,164,68,0.3);
    }


    p{
        font-family: 'Dancing Script', cursive;
        font-size: 3.5em;
    }
</style>