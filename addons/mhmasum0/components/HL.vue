<script setup lang="ts">
defineProps<{
  className: string
}>()
</script>

<template>
  <b :class="className ?? 'text-indigo-500'">
    <slot />
  </b>
</template>