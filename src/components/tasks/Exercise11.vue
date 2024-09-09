<template>
    <form>
        <input type="text" name="fullname" id="fullname" v-on:input="splitFullName" v-model="fullname">
    </form>
    <div>
        <p>First name: {{ firstName }}</p>
        <p>Last name: {{ lastName }}</p>
    </div>
</template>

<script>
    export default {
        name:"Exercise11",
        data(){
            return {
                firstName:"",
                lastName:""
            }
        },
        methods: {
            splitFullName(e){
                let fullname = e.target.value.split(" ")
                this.firstName = fullname[0];
                this.lastName = fullname[1];
            }
        }
    }
</script>