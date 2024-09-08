<template>
    <p class="message">Move the mouse pointer over the box below:</p>
    <div class="box" v-on:mousemove="mousePos"></div>
    <p>x: {{ xPos }}, y: {{ yPos }}</p>
</template>

<script>
    export default {
        name:"Exercise6",
        data(){
            return {
                xPos:0,
                yPos:0
            }
        },
        methods: {
            mousePos(event){
                this.xPos = event.offsetX;
                this.yPos = event.offsetY
            }
        }
    }
</script>

<style>
    .box{
        width: 200px;
        height: 200px;
        border: 1px solid grey;
    }
</style>