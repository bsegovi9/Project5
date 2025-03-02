<script setup>
import { faker } from '@faker-js/faker'

// Random food-related data
const foodName = faker.food.dish() // Random food dish name
const foodDescription = faker.lorem.sentence() // Random food description

// Food image using faker
const foodImageUrl = faker.image.urlLoremFlickr({ category: 'food', height: 480, width: 960 })
</script>

<template>
    <RouterLink :to="{name: 'CardDetail', params: {id: foodName}}">
        <div class="border border-gray-500 rounded-lg shadow bg-gray-400 h-full">
            <!-- Display the food image -->
            <img class="object-fill h-480 w-960 rounded-t-lg" :src="foodImageUrl" />
            <div class="p-4">
                <!-- Display food name -->
                <p class="mb-2 text-2xl font-bold">{{ foodName }}</p>
                <!-- Display food description -->
                <p class="mb-2 text-gray-700">{{ foodDescription }}</p>
            </div>
        </div>
    </RouterLink>
</template>
