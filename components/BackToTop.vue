<template>
    <button
      class="fixed bottom-4 right-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
      @click="scrollToTop">
      Back to Top
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