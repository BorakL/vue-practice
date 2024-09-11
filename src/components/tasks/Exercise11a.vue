<template>
    <input v-model="reversedText" placeholder="Enter reversed text"/>
    <p>Original text: {{ text }}</p>
</template>
  
<script>
export default {
    data: ()=>{
        return {
            text:"asdf"
        }
    },
    computed: {
        reversedText:{
            get() {
                return this.text.split('').reverse().join('');
            },
            set(newValue){
                this.text = newValue.split("").reverse().join("")
            }
        }
    }
};
</script>