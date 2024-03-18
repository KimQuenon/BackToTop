<template>
  <div class="fixed bottom-6 right-6">
    <div class="flex align-center justify-center rounded-full px-1 py-1 w-full" ref="scrollProgress">
      <button
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-4 px-4 rounded-full"
        @click="scrollToTop">
        <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 15l7-7 7 7"/>
        </svg>
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
const scrollToTop = () => {
    window.scrollTo({
      top: 0,
      behavior: 'smooth',
    });
}

const scrollProgress = ref(null);

onMounted(() => {
  let scrollPercentage = () => {
      let pos = window.scrollY;
      let calcHeight = document.documentElement.scrollHeight - document.documentElement.clientHeight;
      let scrollValue = Math.round(pos * 100 / calcHeight);
      console.log(scrollValue);

      scrollProgress.value.style.background = `conic-gradient(#ffff ${scrollValue}%, #c0c0ff ${scrollValue}%)`;
    }

    window.addEventListener("scroll", scrollPercentage);
});

onUnmounted(() => {
  window.removeEventListener("scroll", scrollPercentage);
});
</script>