<template>
  <div class="flex flex-col sm:flex-row bg-white shadow-md rounded-lg overflow-hidden hover:shadow-xl transition mb-6">
    <!-- Thumbnail -->
    <img
      :src="post.thumbnail || 'https://via.placeholder.com/150'" 
      alt="Thumbnail"
      class="w-[150px] h-[150px] sm:w-30 h-30 object-cover sm:rounded-l-lg"
    />

    <!-- Conteúdo -->
    <div class="p-4 flex flex-col justify-center flex-1">
      <router-link :to="`/post/${post.slug}`">
        <h2 class="text-xl font-bold text-blue-700 hover:underline mb-2">
          {{ post.title }}
        </h2>
      </router-link>
      <p class="text-gray-600 text-sm">
        {{ post.description }}
      </p>
    </div>
  </div>
</template>

<script setup>
defineProps({ post: Object });
</script>
