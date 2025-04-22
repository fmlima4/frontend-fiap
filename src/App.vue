<template>
  <div class="min-h-screen bg-gray-100 text-gray-900 font-sans">
    <header class="bg-white shadow p-4 text-center text-2xl font-bold text-gray-600">
      FIAP - Frontend blog - 6AOJR
    </header>

    <main class="max-w-3xl mx-auto p-4">
      <router-view />
      <slot />
    </main>

    <footer class="footer-fixed text-center text-sm text-gray-400 py-4">
      <p>© 2025 - Feito com ❤️</p> Felipe Miranda - 354891 | Rayanne Costa - 353264 | Paulo Ricardo - 353710
    </footer>
  </div>
</template>
