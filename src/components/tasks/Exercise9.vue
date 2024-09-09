<template>
    <form @submit.prevent="submitHandler">
        <div class="input">
            <input type="text" name="name" v-model="name" placeholder="name"/>
        </div>
        <div class="input">
            <input type="text" name="surname" v-model="surname" placeholder="surname">
        </div>
        <div class="input">
            <input type="number" name="age" id="age" v-model="age" placeholder="age">
        </div>
        <div class="input">
            <input type="submit">
        </div>
    </form>
    <div v-on:click.self.once="parentClick" class="parentContainer">
        <button v-on:click.once="childClick">Button1</button>
        <button @click="childClick">Button2</button>
        <hr/>
        <div class="combined" v-on:click="divClickHandler">
            <button v-on:click="bttnClickHandler">Button</button>
        </div>
    </div>
</template>

<script>
    export default {
        name:"Exercise9",
        data: ()=>{
            return {
                name:"",
                surname:""
            }
        },
        methods: {
            submitHandler(){
                console.log(this.name)
                console.log(this.surname)
                console.log(this.age)
            },
            parentClick(){
                console.log("Parent is clicked")
            },
            childClick(){
                console.log("Child is clicked")
            },
            divClickHandler(){
                console.log("Div je kliknut")
            },
            bttnClickHandler(){
                console.log("Button is clicked")
            }
        }
    }
</script>

<style>
    .input{
        margin:10px;
    }
    .parentContainer{
        padding:20px;
    }
</style>