<template>
    <div class="container">
        <h1 class="display-2">List Rendering</h1>
        <div class="row">
            <div class="col">
                <ul class="list-group-flush">
                    <li class="list-group-item text-start border p-1 m-1" v-for="fruit in fruits" :key="fruit">{{ fruit }}</li>
                </ul>
            </div>
        </div>
    </div>
</template>


<script>
    export default {
        data(){
            return {
                fruits: ["banana","apple","peach","melon"]
            }
        },
        methods: {

        }
    }
</script>