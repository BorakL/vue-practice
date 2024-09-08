<template>
    <p>{{ "Moose count: " + count }}</p>
    <button @click="addMoose($event,+1)">+1</button>
    <button @click="addMoose($event,+5)">+5</button>
    <button @click="addMoose($event,-1)">-1</button>
</template>

<script>
    export default {
        name:"Exercise7",
        data: ()=>{
            return {
                count:0
            }
        },
        methods: {
            addMoose($event,number){
                this.count += number;
            }
        }
    }
</script>