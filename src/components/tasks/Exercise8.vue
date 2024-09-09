<template>
    <div @click="showMessage" class="parent">
        <button @click.stop="showMessage2">Dugme 1</button>
        <button @click.stop="showMessage2">Dugme 2</button>
    </div>
</template>

<script>
    export default {
        name: "Exercise8",
        methods: {
            showMessage(){
                window.alert("Roditelj je kliknut")
            },
            showMessage2(){
                window.alert("Dugme je kliknuto")
            }
        },
        data: ()=>{
            return{

            }
        }
    }
</script>

<style>
.parent{
    width:200px;
    height: 200px;
    border:1px solid grey
}
</style>