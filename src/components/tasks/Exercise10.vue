<template>
    <form>
        <div class="inputField">
            <label for="need" id="need">What do you need</label>
            <input type="text" id="need" v-model="need">
        </div>
        <div class="inputField">
            <label for="quantity" id="quantity">How many?</label>
            <input type="number" id="quantity" v-model="quantity">
        </div>
        <div class="inputField">
            <label for="important" id="important">Important?</label>
            <input type="checkbox" id="important" v-model="important">
        </div>
        <input type="submit" @click.prevent="addItem" value="Add item">
    </form>
    <hr>
    <h2>Shopping list:</h2>
    <ul>
        <li 
            v-for="item in items" 
            v-bind:key="item.name" 
            v-show="!item.status"
            v-bind:class="[{underline: item.status}]"
            v-on:click = "item.status=!item.status"
        >
            {{item.need}}
        </li>
    </ul>
    <hr/>
    <ul>
        <li 
            v-for="item in items" 
            v-bind:key="item.name" 
            v-show="item.status"
            v-bind:class="[{underline: item.status}]"
            v-on:click = "item.status=!item.status"
        >
            {{item.need}}
        </li>
    </ul>
</template>

<script>
    export default {
        data(){
            return {
                need: "",
                quantity: 0,
                status: false,
                important: false,
                items:[{
                    need:"Tomatoes",
                    quantity:3,
                    status:false,
                    important: true
                }, 
                {
                    need:"Bread",
                    quantity:1,
                    status:false,
                    important: true
                }]
            }
        },
        methods: {
            addItem(){
                let newItem = {
                    need: this.need,
                    quantity: this.quantity,
                    status: this.status,
                    important: this.important
                };
                this.items.push(newItem)
            }
        }
    }
</script>


<style>
.underline{
    text-decoration: line-through;
}
</style>