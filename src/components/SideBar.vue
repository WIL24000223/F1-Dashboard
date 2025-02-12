<script setup>
</script>

<template>
    <main>
        <div class="w-64 h-screen bg-f1-950 flex flex-col">
            <div class="w-full h-16 flex items-center justify-center font-bold border-0 border-b-2 border-f1-800">
                <h1 class="text-[24px] font-bold">F1 Dash</h1>
            </div>
            <div class="flex flex-col gap-1 py-2">
                <RouterLink to="/" class="p-1.5 mx-4 rounded-md hover:bg-f1-800 transition ease-in-out" activeClass="bg-f1-900">Home</RouterLink>
                <RouterLink to="/drivers" class="p-1.5 mx-4 rounded-md hover:bg-f1-800 transition ease-in-out" activeClass="bg-f1-900">
                    
                    Drivers
                </RouterLink>
            </div>
        </div>
    </main>
</template>