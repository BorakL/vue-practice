<template>
    <div>
        <h1 v-if="isLogin">Dobrodošao</h1>
        <button @click="changeLogin">
            <span v-if="!isLogin" >Login</span>
            <span v-else >Logout</span>
        </button>
    </div>
</template>

<script>
    export default {
        name: "Exercise2",
        data(){
            return {
                isLogin: false
            }
        },
        methods: {
            changeLogin(){
                this.isLogin = !this.isLogin
            }
        }
    }
</script>