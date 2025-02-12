<template>
  <div>
    <h2 class="text-2xl font-bold">{{ title }}</h2>
    <div v-if="loading" class="text-gray-500">Loading comments...</div>
    <div v-else :class="`grid gap-4 ${columns === 4 ? 'grid-cols-4' : 'grid-cols-2'}`">
      <div v-for="comment in comments" :key="comment.id" class="border-b py-2">
        <h3 v-if="fields.includes('name')" class="font-semibold">{{ comment.name }}</h3>
        <p v-if="fields.includes('body')">
          {{ truncateText(comment.body, charLimit) }}
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const props = defineProps({
  limit: { type: Number, required: true }, // Number of comments to fetch
  fields: { type: Array, required: true }, // Controls which fields to show
  title: { type: String, default: "User Comments" }, // Custom title
  columns: { type: Number }, // Number of columns (2 or 4)
  charLimit: { type: Number, default: 100 } // Default character limit (changeable)
});

const comments = ref([]);
const loading = ref(true);

// Function to truncate text based on character limit
const truncateText = (text, charLimit) => {
  return text.length > charLimit ? text.substring(0, charLimit) + "..." : text;
};

onMounted(async () => {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/comments');
    const allComments = await response.json();

    // Shuffle and select random comments
    const shuffled = allComments.sort(() => Math.random() - 0.5);
    comments.value = shuffled.slice(0, props.limit);
  } catch (error) {
    console.error('Error fetching comments:', error);
  } finally {
    loading.value = false;
  }
});
</script>
