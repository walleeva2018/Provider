<template>
  <div>
    <p>This is the Grand Child Component</p>
    <p>{{ message }}</p>
    <button @click="openAnotherComponent">Change Message</button>
  </div>
</template>

<script setup>
import { hasInjectionContext, inject } from 'vue';

// Inject the provided data from the parent component
const { message, openAnotherComponent } = inject('parentData');
if (hasInjectionContext()) {
  console.log('hello');
}
</script>
