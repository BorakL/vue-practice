<template>
    <div>
        <ul>
            <li v-for="(fruit,index) in fruits" :key="fruit"> 
                <span>{{ fruit }}</span>
                <span @click="removeFruit(index)"> x </span>
            </li>
        </ul>
    </div>
    <div>
        <input v-model="newFruit" type="text"/>
        <button @click="addNewFruit"> Dodaj </button>
    </div>
    <p @click="myFoo">Proba</p>
</template>

<script>
    const fruits = ["apple","orange","bananas"];
    export default {
        data(){
            return {
                fruits: fruits,
                newFruit: ''
            }
        },
        methods:{
            addNewFruit(){
                if(this.newFruit){
                    this.fruits.push(this.newFruit);
                    this.newFruit='';
                }
            },
            removeFruit(index){
                this.fruits.splice(index,1)
            }
        }
    }
</script>