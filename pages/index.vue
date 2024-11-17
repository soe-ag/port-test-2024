<script setup lang="ts">
import type { ActiveStock } from "~/utils/type";
import works from "~/public/data/projectData.json";

const fetchData = async (): Promise<ActiveStock[]> => {
  const data = await $fetch<ActiveStock[]>(
    "https://financialmodelingprep.com/api/v3/stock_market/actives?apikey=Ai7NmAPUE7MqHIsSWf4dgsoSvOa658He"
  );

  console.log(data);
  return data.slice(0, 10);
};

const activeStocks = ref<ActiveStock[]>([]);
onMounted(async () => {
  // activeStocks.value = await fetchData();

  const container = document.querySelector(".carousel-container");
  const sections = document.querySelectorAll(".carousel-section");

  let currentSectionIndex = 0;

  container.addEventListener("wheel", (event) => {
    event.preventDefault(); // Prevent default scroll behavior

    if (event.deltaY > 0 && currentSectionIndex < sections.length - 1) {
      // Scroll right
      currentSectionIndex++;
    } else if (event.deltaY < 0 && currentSectionIndex > 0) {
      // Scroll left
      currentSectionIndex--;
    }

    sections[currentSectionIndex].scrollIntoView({
      behavior: "smooth",
      inline: "start",
    });
  });
});
</script>
<!-- eslint-disable vue/html-self-closing -->
<template>
  <div class="text-gray-300">
    <div class="grid grid-cols-2 gap-4">
      <div class="m-2 p-2">
        <div class="flex-col flex gap-2 px-20 text-2xl font-semibold">
          <p>SOE AUNG</p>
          <p>Frontend Developer</p>
          <p class="text-gray-500 text-base">
            Build functional and visually appealing responsive web applications
            <br />
            that bring ideas to life.
          </p>
        </div>
      </div>
      <!-- <div class="m-2 p-2">

      </div> -->
      <div class="carousel-container bg-gray-800 w-200 h-200">
        <div id="section1" class="carousel-section text-xl">
          <div class="px-10 py-2">
            <p class="text-gray-300">
              Frontend engineer skilled in JavaScript, TypeScript, and hands-on
              experience with frameworks like Vue 3 and Nuxt. With a master’s
              degree in engineering, I bring a detail-oriented approach and
              unique perspectives to development.. <br /><br />Enjoy creating
              user-friendly, visually appealing websites and applications that
              bring ideas to life. With a good design sense, I focus on crafting
              interfaces that are both functional and enjoyable for users.<br /><br />
              In addition to web development, I have an interest in 3D modeling,
              crypto, and AI, and I enjoy finding practical ways to integrate
              emerging technologies into modern digital experiences.
            </p>
          </div>
        </div>
        <div id="section2" class="carousel-section text-lg">
          <div class="h-80% flex flex-col gap-2 justify-evenly">
            <!-- <p>Experiences</p> -->
            <div class="m-1">
              <div class="flex gap-2 items-center">
                <!-- <div class="i-material-symbols-code text-blue-400"></div> -->
                <NuxtImg src="/images/code.png" class="w-5 h-5" />

                <p class="text-xl">Frontend Developer @444 (MyNavi Group)</p>
              </div>
              <p class="text-base text-gray-500 font-semibold ml-7">
                2023 July - <span class="underline">Present</span>
              </p>
              <ul class="ml-7 my-2 list-none">
                <li>
                  Migrated Vue2 to Vue3/Nuxt3 for SSR, enhancing performance and
                  maintainability.
                </li>
                <li>
                  Implemented multilingual support with i18n and responsive user
                  interfaces.
                </li>
                <li>
                  Built shared components through Story (Historie) testing.
                </li>
                <li>
                  Resolved feature bugs and carried out new features
                  implementation.
                </li>
              </ul>

              <div class="flex gap-2 text-xl ml-7">
                <div class="i-logos-vue"></div>
                <div class="i-logos-nuxt-icon"></div>
                <div class="i-logos-typescript-icon"></div>
                <div class="i-logos-unocss"></div>
              </div>
            </div>
            <div class="m-1">
              <div class="flex gap-2 items-center">
                <!-- <div class="i-material-symbols-code text-blue-400"></div> -->
                <NuxtImg src="/images/code.png" class="w-5 h-5" />

                <p class="text-xl">Frontend Developer @Egodiva</p>
              </div>
              <p class="text-base text-gray-500 font-semibold ml-7">
                2022 Aug - 2023 May
              </p>

              <ul class="ml-7 my-2 list-none text-lg">
                <li>
                  Developd landing pages that align with the design mock-ups.
                </li>
                <li>
                  Created visually compelling websites to meet the client's
                  marketing goals.
                </li>
                <li>
                  Updated websites according to marketing campaign and SEO
                  standards.
                </li>
              </ul>
              <div class="flex gap-2 text-xl ml-7">
                <div class="i-logos-javascript"></div>
                <div class="i-logos-sass"></div>
                <div class="i-logos-wordpress-icon"></div>
              </div>
            </div>
          </div>
        </div>
        <div id="section3" class="carousel-section flex flex-col gap-2 p-2">
          <div v-for="work in works" :key="work.id" class="w-full">
            <WorkCard
              :id="work.id"
              :title="work.title"
              :description="work.description"
              :image="work.image"
            />
          </div>
        </div>
        <!-- <div id="section4" class="carousel-section">Section 4</div> -->
      </div>
    </div>
    <a href="https://www.flaticon.com/free-icons/code" title="code icons"
      >Code icons created by meaicon - Flaticon</a
    >
  </div>
</template>

<style scoped>
.carousel-container {
  /* overflow: hidden;  Hide overflow content */
  display: flex; /* Flex layout for horizontal alignment */
  scroll-snap-type: x mandatory; /* Enable horizontal snap scrolling */
  overflow-x: scroll; /* Horizontal scroll enabled */
  scrollbar-width: none; /* Hide scrollbar (Firefox) */
}

.carousel-container::-webkit-scrollbar {
  display: none; /* Hide scrollbar (WebKit) */
}

.carousel-section {
  flex: 0 0 100%; /* Each section takes 100% of the container's width */
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  /* background-color: lightblue; */
  scroll-snap-align: start; /* Snap each section to the start of the container */
  /* border: 1px solid #555; */
}
</style>
