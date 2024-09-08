<template>
    <div>
        <p v-show="!textHidden">Some text</p>
        <button v-if="textHidden" @click="changeTextHiden">Show text</button>
        <button v-else @click="changeTextHiden">Hide text</button>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                textHidden: true
            }
        },
        methods: {
            changeTextHiden(){
                this.textHidden = !this.textHidden
            }
        }
    }
</script>