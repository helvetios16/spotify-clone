<template>
  <div class="flex items-center gap-5 relative overflow-hidden">
    <picture class="w-16 h-16 bg-theme-black-secondary rounded-md shadow-lg overflow-hidden">
      <img :src="image" :alt="title" />
    </picture>
    <div class="flex flex-col">
      <h3 class="font-semibold text-sm block">
        {{ title }}
      </h3>
      <span class="text-xs opacity-80"> {{ artists.join(', ') }} </span>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  image: string;
  title: string;
  artists: string[];
}>();
</script>
