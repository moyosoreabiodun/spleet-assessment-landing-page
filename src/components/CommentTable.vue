<template>
    <div>
      <h2 class="text-2xl font-bold text-center mb-4">{{ title }}</h2>
  
      <table v-if="tableData.length" class="w-full border-collapse border border-gray-300">
        <tbody>
          <tr v-for="(row, rowIndex) in tableData" :key="rowIndex">
            <td v-for="(cell, cellIndex) in row" :key="cellIndex" class="border p-2 text-center">
              {{ cell }}
            </td>
          </tr>
        </tbody>
      </table>
  
      <p v-else class="text-center text-red-500">No data available.</p>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  
  const props = defineProps({
    title: { type: String, default: "Short Comment Table" }
  });
  
  const tableData = ref([]);
  
  onMounted(async () => {
    try {
      const response = await fetch('https://jsonplaceholder.typicode.com/comments');
      const allComments = await response.json();
  
      // Extract the first 4 words from each comment body
      const truncatedComments = allComments
        .map(comment => comment.body.split(' ').slice(0, 4).join(' ')); // ✅ Always gets 4 words
    
      // Shuffle and select 12
      const shuffled = truncatedComments.sort(() => Math.random() - 0.5).slice(0, 12);
  
      // Ensure 3x4 structure
      tableData.value = [
        shuffled.slice(0, 4),
        shuffled.slice(4, 8),
        shuffled.slice(8, 12)
      ];
    } catch (error) {
      console.error("Error fetching comments:", error);
    }
  });
  </script>
  