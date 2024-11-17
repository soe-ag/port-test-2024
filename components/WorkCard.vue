<script setup lang="ts">
defineProps<{
  id: number;
  title: string;
  description: string;
  image: string;
}>();
</script>

<template>
  <div
    class="flex gap-4 justify-between items-center text-gray-300 p-4 relative"
  >
    <!-- <div
      class="absolute b-t-1 b-l-1 b-solid b-b-0 b-r-0 b-blue-400 top-0 left-0 w-4 h-4"
    /> -->
    <div class="w-60%">
      <div class="mb-2 flex gap-2 items-center">
        <p class="">{{ title }}</p>
        <div class="i-material-symbols-open-in-new hover:cursor-pointer"></div>
      </div>
      <p class="text-gray-400">
        {{ description }}
      </p>
    </div>
    <div class="">
      <NuxtImg :src="image" width="250" class="m-auto rounded-2" />
    </div>
    <!-- <div
      class="absolute b-t-0 b-l-0 b-solid b-b-1 b-r-1 b-blue-400 bottom-0 right-0 w-4 h-4"
    /> -->
  </div>
</template>
