<script setup lang="ts">
defineProps<{
  id: number;
  title: string;
  description: string;
  image: string;
  link: string;
  github: string;
}>();
</script>

<template>
  <div
    class="flex flex-col gap-4 justify-evenly text-gray-300 relative max-w-75"
    :class="{ 'items-start': id % 2 === 1, 'items-end': id % 2 === 0 }"
  >
    <!-- <div
      class="absolute b-t-1 b-l-1 b-solid b-b-0 b-r-0 b-blue-400 top-0 left-0 w-4 h-4"
    /> -->
    <div class="w-full mt-2">
      <div
        class="flex gap-2"
        :class="{ 'justify-start': id % 2 === 1, 'justify-end': id % 2 === 0 }"
      >
        <NuxtLink
          class="decoration-none text-gray-200 hover:text-blue-400 font-semibold"
          :to="link"
        >
          <p class="text-sm text-wrap">{{ title }}</p>
        </NuxtLink>
        <!-- <NuxtLink :to="github" target="_blank">
          <div
            class="i-simple-icons-github text-white text-xl hover:text-blue-300"
          />
        </NuxtLink> -->
        <!-- <div class="i-material-symbols-open-in-new hover:cursor-pointer"></div> -->
      </div>
      <!-- <p class="text-gray-400 text-sm lg:text-base">
        {{ description }}
      </p> -->
    </div>
    <NuxtLink class="" :to="link" target="_blank">
      <NuxtImg
        :src="image"
        class="m-auto rounded-2 b-2 b-solid w-40 lg:w-60 hover:b-blue-400 b-gray-600 hover:cursor-pointer"
      />
    </NuxtLink>
    <!-- <div
      class="absolute b-t-0 b-l-0 b-solid b-b-1 b-r-1 b-blue-400 bottom-0 right-0 w-4 h-4"
    /> -->
  </div>
</template>
