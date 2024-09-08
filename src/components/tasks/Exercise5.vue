<template>
    <h1>Hello world</h1>
    <p v-bind:style="{color: textColor}">Text text text...</p>
    <button @click="changeColor">Change color</button>
</template>

<script>
    export default {
        data(){
            return {
                textColor:"red"
            }
        },
        methods: {
            changeColor(){
                this.textColor = this.textColor==="green" ? "red" : "green";
            }
        }
    }
</script>

<style> 
</style>