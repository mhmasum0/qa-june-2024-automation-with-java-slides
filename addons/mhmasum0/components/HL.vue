<script setup lang="ts">
defineProps<{
  className: string
}>()
</script>

<template>
  <b :class="className ?? 'text-green-500 bg-green-100 p-1'">
    <slot />
  </b>
</template>