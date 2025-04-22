<template>
  <div>
    <button
      @click="fetchWords"
      class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded mb-6"
    >
      Gerar Novos Cards
    </button>

    <PostCard v-for="post in posts" :key="post.id || post.slug" :post="post" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import PostCard from '../components/PostCard.vue';
import { posts as staticPosts } from '../data/posts'; // posts estáticos

const posts = ref([...staticPosts]); // Inicializa com os posts originais

// Função para buscar novas palavras e adicionar como novos cards
async function fetchWords() {
  try {
    const response = await fetch("/api/palavras")
    const data = await response.json();

    // Transforma as palavras no mesmo formato dos seus posts
    const newPosts = data.map((item, index) => ({
      id: `${item.id}`,
      slug: item.slug,
      title: item.title,
      description: item.description,
      content: item.content,
      thumbnail: item.thumbnail
    }));

    posts.value.push(...newPosts);
  } catch (error) {
    console.error('Erro ao buscar palavras:', error);
  }
}
</script>
