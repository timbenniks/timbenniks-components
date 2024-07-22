<script setup lang="ts">
defineProps(["copy"]);
</script>

<template>
  <div
    v-if="copy"
    class="px-4 md:px-8 mb-8 prose prose-xl prose-invert max-w-none"
    v-html="copy"
  />
</template>
