<script setup>

import {ref} from 'vue'

        const firstName = ref('');
        const lastName = ref('');
        const address = ref('');
        const entries = ref([]);

        const addEntry = () => {
            entries.value.push({
                firstName : firstName.value,
                lastName : lastName.value,
                address : address.value
            });
            firstName.value = '' ;
            lastName.value = '' ;
            address.value = '' ;
        };

        const deleteEntry = (index) => {
        entries.value.splice(index, 1);
        };

</script>

<template>
    <div class="customerDetails">
        <form @submit.prevent="addEntry">
            <label for="firstName">First Name:</label>
            <input type="text" id="firstName" v-model="firstName" required><br>
            <label for="lastName">Last Name:</label>
            <input type="text" id="lastName" v-model="lastName" required><br>
            <label for="address">Address:</label>
            <input type="text" id="address" v-model="address" required><br>
            <button type="submit">Add</button>
        </form>
    </div>
    <h2><b>Enteries</b></h2>
    <div>
        <table style=" border: 1px solid wheat; margin: 5px;">
            <thead>
                <tr>
                    <th style="border: 1px solid whitesmoke;">FirstName</th>
                    <th style="border: 1px solid whitesmoke;">LastName</th>
                    <th style="border: 1px solid whitesmoke;">Address</th>
                    <th style="border: 1px solid whitesmoke;">Action</th>
                </tr>
            </thead>
            <tbody>
                <tr class="output" v-for="(entry , index) in entries" :key="index" >
                    <td>{{ entry.firstName }}</td>
                    <td>{{ entry.lastName }}</td>
                    <td>{{ entry.address }}</td>
                    <td><button @click="deleteEntry(index)">Delete</button></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<style>
.customerDetails{
    border: 2px solid whitesmoke;
    
}

td{
    border: 1px solid white;
}

button{
    background-color: cyan;
    color: black;
}
thead{
    order: 1px solid white;
}


</style>