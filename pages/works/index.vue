<script setup lang="ts">
import Timeline from "primevue/timeline";

const items = ref([
  {
    id: 1,
    title: "Old Portfolio Website",
    description: "work.description",
    image: "/images/oldworks/part-old-port.png",
    link: "https://portfolio0223.netlify.app/",
    github: "https://github.com/soe-ag/portfolio_2023feb",
  },
  {
    id: 2,
    title: "Botha  Gallery Website",
    description: "work.description",
    image: "/images/oldworks/part-botha-gallery.png",
    link: "https://lp.bo-tha.com/official_character_gallery/202212/",
    github: "https://github.com/soe-ag/botha_compe_artlist",
  },
  {
    id: 3,
    title: "Botha Official Website",
    description: "work.description",
    image: "/images/oldworks/part-botha.png",
    link: "https://soe-ag.github.io/botha_about_clone/",
    github: "https://github.com/soe-ag/botha_about_clone",
  },
  {
    id: 4,
    title: "Botha Competition Website",
    description: "work.description",
    image: "/images/oldworks/part-botha-competition.png",
    link: "https://soe-ag.github.io/botha_compete_clone/",
    github: "https://github.com/soe-ag/botha_compete_clone",
  },
  {
    id: 5,
    title: "Egodiva Marketing Website",
    description: "work.description",
    image: "/images/oldworks/part-egodia-marketing.png",
    link: "https://soe-ag.github.io/egodiva_marketing_clone/",
    github: "https://github.com/soe-ag/egodiva_marketing_clone",
  },
]);
</script>

<template>
  <div class="p-4 md:p-6 max-w-180 m-auto">
    <h3 class="text-center mb-8">Past Works</h3>
    <!-- <section class="grid grid-cols-1 sm:grid-cols-2 gap-6"></section> -->

    <Timeline :value="items" align="alternate" class="customized-timeline">
      <template #marker="slotProps">
        <span
          class="flex w-8 h-8 items-center justify-center text-white rounded-full z-10 shadow-sm"
        >
          <NuxtLink :to="slotProps.item.github" target="_blank">
            <div
              class="i-simple-icons-github text-white text-2xl hover:text-blue-300"
            />
          </NuxtLink>
        </span>
      </template>
      <template #content="slotProps">
        <ArchiveCard
          :id="slotProps.item.id"
          :title="slotProps.item.title"
          :description="slotProps.item.description"
          :image="slotProps.item.image"
          :link="slotProps.item.link"
          :github="slotProps.item.github"
        />
      </template>
    </Timeline>
  </div>
</template>
