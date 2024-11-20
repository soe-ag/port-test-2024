<script setup lang="ts">
import ScrollTop from "primevue/scrolltop";
</script>

<template>
  <div class="mx-auto py-8 flex justify-center max-w-250">
    <div class="main flex flex-col gap-6 text-gray-400">
      <section class="grid grid-cols-2 gap-4">
        <div class="flex flex-col gap-4">
          <div>
            <NuxtLink
              class="flex gap-2 items-center mb-2 hover:cursor-pointer hover:text-blue-300 text-blue-400 decoration-none"
              :to="'https://movie-db-beta.netlify.app/'"
              target="_blank"
            >
              <h2 class="">Personalized Movies Database</h2>

              <div class="i-material-symbols-open-in-new text-2xl" />
            </NuxtLink>
            <div class="flex gap-4 items-center mb-2">
              <h3 class="text-gray-300">Overview</h3>
              <NuxtLink
                :to="'https://github.com/soe-ag/practice-local-movie-source'"
                target="_blank"
              >
                <div
                  class="i-simple-icons-github text-white text-xl hover:text-blue-300"
                />
              </NuxtLink>
            </div>

            <p class="text-sm">
              This project started from a simple wish, having my own database to
              store and organize my favorite movies and TV series. I had tried
              using IMDb for tracking my watch list and favorites, but I found
              the interface a bit clunky and heavy for my needs. So, I set out
              to create a personalized, lightweight solution. This is just Phase
              1 of the project, and I'll continue adding features based on what
              I find useful, with plans for a Phase 2 release in the future.
            </p>
          </div>
          <div>
            <h3 class="text-gray-300 mb-2">Features</h3>
            <ul class="ml-4 text-sm mb-2">
              <li>
                Discover Trending Movies: Check out the latest popular movies.
              </li>
              <li>Search Movies and TV Series: Easily look up titles.</li>
              <li>
                Track What to Watch: Keep a list of movies and series to watch
                later.
              </li>
              <li>
                Save Favorites: Collect all my favorite titles in one place for
                quick access.
              </li>
            </ul>
            <p class="text-sm">
              This app is designed to make tracking my favorite content simple,
              convenient, and tailored to my preferences.
            </p>
          </div>
        </div>
        <NuxtLink
          :to="'https://movie-db-beta.netlify.app/'"
          target="_blank"
          class="m-auto"
        >
          <NuxtImg
            src="/images/full-movie.png"
            width="450"
            class="rounded-2 b-2 b-solid hover:b-blue-400 b-transparent"
          />
        </NuxtLink>
      </section>

      <section class="grid grid-cols-2 gap-4">
        <div class="p-2 m-auto flex justify-center gap-8 text-3xl">
          <div class="i-logos-vue" />
          <div class="i-logos-nuxt-icon" />
          <div class="i-logos-unocss" />
          <div class="i-logos-supabase-icon" />
        </div>
        <div>
          <h3 class="text-gray-300 mb-2">Stack and explanation</h3>
          <p class="text-sm">
            I have a solid foundation in Vue, and for this project, I decided to
            work with Nuxt to incorporate server-side rendering (SSR) and take
            advantage of Nuxt’s straightforward routing features. Since I use
            UnoCSS at work, I chose it here as well for a familiar, efficient
            styling experience, aiming to get the job done with my most-used
            tools rather than focusing on the "perfect" stack. I originally went
            with Firebase for the database, but I switched to Supabase because
            it just worked better for what I needed, and the documentation made
            things a lot easier to follow. Firebase felt a bit complicated since
            it needs different setups for client and server, plus specific SDKs
            like Firebase Admin on the server side.
          </p>
        </div>
      </section>

      <section class="grid grid-cols-2 gap-4">
        <div>
          <h3 class="text-gray-300 mb-2">Problems and thought process</h3>
          <p class="text-sm">
            I initially started with local storage for saving data since I
            wasn’t familiar with Firebase or Supabase yet. But as the project
            evolved, I wanted access to my data from any device, which local
            storage couldn’t offer.
            <!-- Plus, I wanted to challenge myself with new
            technologies. Switching to Supabase opened up more possibilities,
            like adding authentication, querying, and filtering—making data
            manipulation easier.  -->
            The first hurdle was setting up the environment and dependencies
            without breaking anything in the existing project. After a lot of
            trial and error, I got it running smoothly. Next, I tackled
            Supabase’s built-in auth, setting up user accounts for secure data
            access. Initially, I’d written everything as client-side API calls,
            but eventually refactored for server-side rendering where it made
            sense, which streamlined data handling on page load.
            <!-- Along
            the way, I cleaned up my code to make it reusable and followed some
            best practices from my work environment, even though this was a
            personal project. There were plenty of challenges along the way, but
            by diving into the docs, troubleshooting with ChatGPT, and plenty of
            debugging, I wrapped up Phase 1 of my project! -->
          </p>
        </div>
        <div class="p-2 m-auto">
          <NuxtImg
            src="/images/other/question-round.svg"
            width="200"
            class="-rotate-10"
          />
        </div>
      </section>

      <section class="grid grid-cols-2 gap-4">
        <div class="p-2 m-auto">
          <NuxtImg
            src="/images/other/study-round.svg"
            width="300"
            class="rotate-10"
          />
        </div>
        <div>
          <h3 class="text-gray-300 mb-2">Lessons learned</h3>
          <p class="text-sm">
            Working on this project has been a huge learning experience,
            especially in building something from scratch. I’ve gained a solid
            understanding of Nuxt, Supabase, and API implementation, along with
            the skills to troubleshoot bugs effectively. In the beginning, I
            focused on getting each feature working, which meant writing simpler
            code to keep things moving. Later, I went back to refactor it for
            reusability and clarity, knowing that would make it easier to expand
            in the future. Since I didn’t start with a defined design or
            component structure, I found myself constantly writing, deleting,
            and editing to improve readability and maintainability. This
            approach worked, but I realized how much easier things would have
            been with a good design and structure from the start. It would’ve
            saved time, reduced rework, and probably prevented a few headaches
            along the way 😄.
          </p>
        </div>
      </section>

      <section>
        <h3 class="text-gray-300 mb-2">Features plan to add later</h3>
        <ul class="ml-4 text-sm">
          <li>
            Sorting the watchlist and favorites by rating and release year
          </li>
          <li>
            Adding filters for custom views, like by year, rating, or type
          </li>
          <li>Enhancing the UI for a more visually appealing experience</li>
          <li>
            Expanding API calls to include more data, like top movies of 2024 or
            highest-rated IMDb films
          </li>
        </ul>
      </section>

      <NuxtLink
        :to="'/works/asset-tracker'"
        class="text-right text-sm decoration-none text-blue-400 hover:text-blue-300 flex gap-2 justify-end items-center"
        ><p>To Next Project</p>
        <div
          class="i-material-symbols-arrow-circle-right text-xl animate-pulse"
      /></NuxtLink>
    </div>
    <ScrollTop
      :pt="{
        root: { class: 'bg-blue-400! b-none!' },
      }"
    />
  </div>
</template>
