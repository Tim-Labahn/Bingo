<script setup lang="ts">
import Row from "./Row.vue";

const gridColumnCount = 5;

defineProps<{ card: string[][] }>();
</script>

<template>
  <div></div>
  <div
    v-for="row in card"
    :style="{
      display: 'grid',
      gridTemplateColumns: `repeat(${gridColumnCount}, 1fr)`,
      width: '700px',
    }"
  >
    <Row :row="row"></Row>
  </div>
</template>
