<template>
  <div class="container mx-auto">
    <div class="flex flex-col items-center justify-center min-h-screen">
      <h1 class="text-4xl md:text-6xl font-semibold text-center text-gray-800 mb-8">
        Welcome to today's Class
      </h1>
      <p class="text-lg md:text-xl text-gray-600 text-center">
        Let's understand a concept. This is the parent component.
      </p>
      <button
        @click="openAnotherComponent"
        class="mt-8 px-4 py-2 bg-blue-500 text-white font-semibold rounded hover:bg-blue-600 focus:outline-none focus:bg-blue-600"
      >
        <span v-if="showChild">Close Child Component</span>
        <span v-else>Open Child Component</span>
      </button>
      <ChildComponent v-if="showChild" />
    </div>
  </div>
</template>

<script setup>
import { ref, provide } from 'vue';
import ChildComponent from '../components/ChildComponent.vue';

const showChild = ref(false);

const openAnotherComponent = () => {
  showChild.value = !showChild.value;
};

// Provide data and functionality to child components
provide('parentData', {
  showChild,
  openAnotherComponent
});
</script>

<style>
.container {
  padding: 0 1rem;
}

@media (min-width: 640px) {
  .container {
    max-width: 640px;
  }
}

@media (min-width: 768px) {
  .container {
    max-width: 768px;
  }
}

@media (min-width: 1024px) {
  .container {
    max-width: 1024px;
  }
}

@media (min-width: 1280px) {
  .container {
    max-width: 1280px;
  }
}

@media (min-width: 1536px) {
  .container {
    max-width: 1536px;
  }
}
</style>
