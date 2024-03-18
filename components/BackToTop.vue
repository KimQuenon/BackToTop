<template>
  <button
    class="fixed bottom-6 right-6 bg-blue-500 hover:bg-blue-700 text-white font-bold py-3 px-3 rounded-full"
    @click="scrollToTop">
    <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 15l7-7 7 7"/>
    </svg>
  </button>
</template>

<script setup>
  const scrollToTop = () => {
      window.scrollTo({
        top: 0,
        behavior: 'smooth',
      });
  }
</script>