<script setup lang="ts">
import Row from "./Row.vue";

const gridColumnCount = 5;

defineProps<{ card: string[][] }>();
</script>

<template>
  <div
    v-for="row in card"
    :style="{
      display: 'grid',
      gridTemplateColumns: `repeat(${gridColumnCount}, 1fr)`,
      width: '1000px',
    }"
  >
    <Row :row="row"></Row>
  </div>
</template>
