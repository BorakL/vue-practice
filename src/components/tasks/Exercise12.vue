<template>
    <div class = "conainer bg-primary border text-white p-5">
        <div class="row">
            <div class="col">
                <h1 class="display-1 text-centered text-md-start">Price format:</h1>
            </div>
        </div>
        <div class="row">
            <div class="col-md-2 ">
                <p class="text-sm-centered text-lg-end">Enter Price:</p>
            </div>
            <div class="col-md-10">
                <input class="form-control" v-model="formatedPrice" placeholder="price"/>
            </div>  
        </div>
    </div>
</template>

<script>

    export default {
        name: "Exercise12",
        data(){
            return {
                price:0
            }
        },
        methods: {

        },
        computed: {
            formatedPrice:{
                get(){
                    return `$ ${this.price}`
                },
                set(newValue){
                    this.price = parseFloat(newValue.replace(/\$/g, '')) || 0;
                }
            }
        }
    }
</script>