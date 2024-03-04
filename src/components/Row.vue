<script setup lang="ts">
import Tile from "./Tile.vue";

defineProps<{ row: string[] }>();
</script>
<template>
  <div v-for="tile in row">
    <Tile :tile="tile"></Tile>
  </div>
</template>
