<script>
    export default { 
        // Add code in appropriate places
        data() {
            return {
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
                newItem : "",
            }
            
        },
        computed: {},
        methods : {
            deleteItem(item) {
                const index = this.items.indexOf(item);
                if (index > -1) { // only splice array when item is found
                    this.items.splice(index, 1); // 2nd parameter means remove one item only
                }
            },
            addItem(item) {
                if (item !== "") {
                    this.items.push(item);
                }
            }
        }
    }
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <ul>
        <li v-for="item in items">{{item}}
            <strong @click="deleteItem(item)"> Delete! </strong>
        </li>
    </ul>

    <input v-model="newItem"></input>
    <button @click="addItem(newItem)">Add!</button>
   
</template>
