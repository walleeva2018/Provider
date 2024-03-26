<template>
  <div class="child-container">
    <p>This is a child component</p>
    <button @click="toggleGrandChild" class="toggle-button">
      <span v-if="showGrandChild">Close GrandChild</span>
      <span v-else>Open GrandChild</span>
    </button>
    <template v-if="showGrandChild">
      <GrandChild />
    </template>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import GrandChild from './GrandChildComponent.vue';

const showGrandChild = ref(false);

const toggleGrandChild = () => {
  showGrandChild.value = !showGrandChild.value;
};
</script>

<style scoped>
.child-container {
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  background-color: #f9f9f9;
  margin-bottom: 20px;
}

.toggle-button {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  margin-bottom: 10px;
}

.toggle-button:hover {
  background-color: #0056b3;
}

.toggle-button:active {
  background-color: #004080;
}
</style>
