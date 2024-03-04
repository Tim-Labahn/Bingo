<script setup lang="ts">
import { ref, defineProps } from "vue";

defineProps<{ tile: string }>();

const checked = ref(false);

const toggleChecked = () => {
  checked.value = !checked.value;
};
</script>

<template>
  <div class="tile-container">
    <div class="tile" :class="{ checked: checked }" @click="toggleChecked">
      <span class="tile-text">{{ tile }}</span>
    </div>
    <div v-if="checked" class="overlay" @click="toggleChecked"></div>
  </div>
</template>

<style scoped>
.tile-container {
  position: relative;
}

.tile {
  border: 0.5px solid black;
  box-sizing: border-box;
  width: 200px;
  height: 200px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  font-size: 1.8rem; /* Initial font size, adjust as needed */
  user-select: none;
  cursor: pointer; /* Add this to indicate it's clickable */
}

.tile-text {
  z-index: 1;
  max-width: 90%; /* Adjust as needed */
  text-align: center;
}

.overlay {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 80%;
  height: 80%;
  background: radial-gradient(circle, transparent 60%, red 1%);
  border-radius: 50%;
  pointer-events: none; /* Prevents overlay from blocking clicks on underlying elements */
}
</style>
