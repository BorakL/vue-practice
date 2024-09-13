<template>
    <div class="container">
        <h1 class="display-2">List Rendering</h1>
        <div class="row main">
            <div class="col-md-6">
                <ul class="list-group-flush">
                    <li 
                        class="list-group-item text-start border p-1 m-1" 
                        v-for="fruit in fruits" 
                        :key="fruit"
                        v-on:click="showMessage(fruit)"
                        v-bind:style="{color: fruit==='banana' ? 'orange' : '', textDecoration: fruit===selectedFruit ? 'underline': 'none'}"
                    >
                            {{ fruit }}
                    </li>
                </ul>
            </div>
            <div class="col-md-6 selectedFruitContainer border p-2 bg-primary text-white display-2 d-flex justify-content-center align-items-center">
                {{ selectedFruit }}
                <div class="removeBtn" v-on:click="removeFruit(selectedFruit)">x</div>
            </div>
        </div>
        <div class="row">
            <div class="col mt-3">Count: {{ count }}</div>
        </div>
        <div class="row">
            <div class="col-7 d-flex aligin-items-center justify-content-around">
                <label for="fruit" class="me-2">New fruit: </label>
                <input id="fruit" type="text" class="form-control me-2" v-model="newFruit">
                <button type="button" class="btn btn-primary" v-on:click="addNewFruit">Add fruit</button>
            </div>
            <div class="col-5">
                <p class="text-start pt-2">{{ errorMessage }}</p>
            </div>
        </div>
    </div>
</template>


<script>
    export default {
        data(){
            return {
                fruits: ["banana","apple","peach","melon"],
                selectedFruit: "",
                newFruit: "",
                errorMessage: ""
            }
        },
        methods: {
            showMessage(fruit){
                this.selectedFruit = fruit
            },
            addNewFruit(){
                this.errorMessage="";
                if(this.newFruit === "") {
                    this.errorMessage = "The field is empty";
                } else if( this.fruits.some(value => this.newFruit===value) ) {
                    this.errorMessage = "This fruit is already exists"
                    this.newFruit = "";
                } else{
                    this.fruits.push(this.newFruit);
                    this.newFruit = ""
                }
            },
            removeFruit(fruit){
                this.fruits = this.fruits.filter(f => f!==fruit);
                this.selectedFruit = ""
            }
        },
        computed: {
            count: {
                get(){
                    return this.fruits.length
                }
            }
        }
    }
</script>

<style>
.selectedFruitContainer{
    position: relative;
}
.removeBtn{
    font-size: 30px;
    position: absolute;
    top: 0;
    right: 10px;
    color: red;
    cursor: pointer;
}
</style>