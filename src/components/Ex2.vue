<script>
    export default { 
        // Add code in appropriate places
        data() {
            return {
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
                newitem: ""
            }
        },
        methods: {
            add(newitem) {
                this.items.push(newitem)
            },
            deleteitem(index) {
                this.items.splice(index, 1)
            }
        }
    }
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <ul>
        <li v-for="(item,index) in items">
            {{item}}
            <button @click="deleteitem(index)">Delete!</button>
        </li>
    </ul>

    <input type="text" v-model="newitem">
    <button @click="add(newitem)">Add!</button>
   
</template>
