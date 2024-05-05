<template>
  <div>
    <!-- Element input teks -->
    <input
      type="text"
      v-model="inputText"
      @input="handleInput"
      :class="{ 'input-error': isError }"
      :style="{ backgroundColor: inputText === '' ? 'lightcoral' : 'transparent' }"
      placeholder="Type something..."
    />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const inputText = ref('');
const isError = ref(false);

const handleInput = () => {
  isError.value = inputText.value === '';
}
</script>

<style scoped>
.input-error {
  border: 2px solid red;
}
</style>
