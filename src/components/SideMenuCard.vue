<template>
  <RouterLink
    :to="`/playlist/${id}`"
    class="playlist-item flex relative p-2 overflow-hidden items-center gap-3 rounded-md hover:bg-zinc-500"
  >
    <picture class="h-12 w-12 flex-none">
      <img
        :src="cover"
        :alt="`Cover of ${title} by ${artistString}`"
        class="object-cover w-full h-full rounded-md"
      />
    </picture>
    <div class="flex flex-auto flex-col truncate">
      <h4 class="text-sm text-white">
        {{ title }}
      </h4>
      <span class="text-xs text-gray-400">
        {{ artistString }}
      </span>
    </div>
  </RouterLink>
</template>
<script setup lang="ts">
import { type Playlist } from '@/lib/data';

const props = defineProps<{
  playlist: Playlist;
}>();

const { id, title, cover, artists } = props.playlist;

const artistString = artists.join(', ');
</script>
