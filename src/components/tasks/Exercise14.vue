<template>
    <div class="container-fluid bg-primary text-white p-3">
        <h1 class="display-2">Simple Two-Way Binding</h1>
        <div class="row p-3">
            <div class="col-md-4 col-lg-2 mb-4">
                <input type="text" v-model="message" class="form-control">
            </div>
            <div class="col-md-8 col-lg-10 bg-danger">
                <p class="text-md-start p-2">{{ message }}</p>
            </div>
        </div>
    </div>

</template>

<script>
    export default {
        name: "Exercise14",
        data(){
            return {
                message: "a"
            }
        },
        computed: {
             
        }
    }
</script>