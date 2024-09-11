<template>
    <div class="container">
        <div class="row">
                <h1 class="display-2">Basic Conditional Rendering</h1>
            <div class="col-md-6 col-lg-4">
                <button v-on:click="showMessage=!showMessage">Show message</button>
            </div>
            <div class="col-md-6 col-lg-8">
                <p v-if="showMessage" class="message">{{ message }}</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                showMessage:true,
                message:"This is message lorem33 adf lorem33 adf lorem33 adf lorem33 adf lorem33 adf lorem33 adf lorem33 adf lorem33 adf"
            }
        }
    }
</script>