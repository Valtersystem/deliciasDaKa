<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';
import SubHeader from '@/Components/SubHeader.vue';
import ProductGrid from '@/Components/ProductGrid.vue';
</script>

<template>
    <AppLayout title="Products">
        <div class="px-4">
            <div class="max-w-8xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                    <SubHeader />
                    <ProductGrid />
                </div>

            </div>
        </div>
    </AppLayout>
</template>
