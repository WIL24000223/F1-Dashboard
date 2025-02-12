<script setup>
import axios from "axios";
import { ref } from "vue";
let search = ref("");
const data = ref({});
axios.get("https://api.openf1.org/v1/drivers?session_key=latest").then((response) => {
    data.value = Array.from(new Set(response.data.map(JSON.stringify))).map(JSON.parse);
    console.log(data.value);
});

function filteredList() {
    return data.value.filter((driver) => 
    (driver.full_name).toLowerCase().includes(search.value.toLowerCase())
)};
</script>

<template>
    <div class="w-full h-screen grid place-content-center">
        <div class="flex flex-col gap-4">
            <input type="text" v-model="search" placeholder="search drivers..." class="p-4 bg-f1-800 rounded-md min-w-80 hover:bg-f1-700 transition ease-in-out focus:outline-0 focus:bg-f1-700" />
            <div class="flex flex-col gap-2 max-h-80 overflow-y-scroll">
                <RouterLink :to="`/drivers/${ driver.driver_number }`" v-for="driver in filteredList()" :key="driver.driver_number" class="p-4 py-2 border-3 border-f1-800 rounded-md hover:bg-f1-700 transition ease-in-out">
                    <p  >{{ driver.full_name }}</p>
                </RouterLink>
            </div>
        </div>
    </div>
</template>