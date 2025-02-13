<template>
    <div class="border rounded-lg p-2 bg-white text-center mx-2 w-60">
      <p class="font-bold text-blue-200">{{ plan }}</p>
      <h4 class="font-bold text-black-500 mt-2">{{ price }}</h4>
      <p class="text-gray-600 mt-2">{{ description }}</p>
      <button class="mt-4 bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-blue-600">
        {{ buttonText }}
      </button>
    </div>
  </template>
  
  <script setup>
  defineProps({
    plan: String,
    price: String,
    description: String,
    buttonText: String
  });
  </script>
  