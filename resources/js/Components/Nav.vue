<script setup>
import NavLink from '@/Components/NavLink.vue';
</script>

<template>
    <div class="flex lg:h-screen flex-col justify-between items-center border-e bg-white">
        <div class="lg:px-4 lg:px-4py-6 flex lg:flex-col flex-row items-start lg:items-center justify-center lg:gap-0 gap-4">

            <img src="../../../public/imagens/ka.png" alt="logo" class="w-20">

            <ul class="mt-6 space-y-1 flex lg:flex-col flex-row items-center lg:items-start">

                <li>
                    <NavLink :href="route('products')" :active="route().current('products')">
                    <a href=""
                        class="block rounded-lg px-4 py-2 text-sm font-medium text-gray-500">
                        Products
                    </a>
                    </NavLink>

                </li>

                <li>
                    <a href=""
                        class="block rounded-lg px-4 py-2 text-sm font-medium text-gray-500">
                        Categories
                    </a>
                </li>
            </ul>
        </div>
    </div>
</template>


