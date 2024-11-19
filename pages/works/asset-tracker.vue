<script setup lang="ts">
import ScrollTop from "primevue/scrolltop";
</script>

<template>
  <div class="mx-auto py-8 flex justify-center max-w-250">
    <div class="main container flex flex-col gap-6 text-gray-400">
      <section class="grid grid-cols-2 gap-4">
        <div class="flex flex-col gap-4">
          <div>
            <NuxtLink
              class="flex gap-2 items-center mb-2 hover:cursor-pointer hover:text-blue-300 text-blue-400 decoration-none"
              :to="'https://asset-tracker-beta.netlify.app/'"
              target="_blank"
            >
              <h2 class="">Asset Tracker</h2>

              <div class="i-material-symbols-open-in-new text-2xl" />
            </NuxtLink>
            <h3 class="text-gray-300 mb-2">Overview</h3>
            <p class="text-sm">
              I have been using TradingView to track stocks, cryptocurrencies,
              and indices for personal investing. While it offers extensive
              tools and features, I wanted a simpler, personalized dashboard to
              quickly access my favorite assets and customize how I interact
              with charts. This project aims to address that need, starting with
              Phase 1, which includes core functionalities. Future updates in
              Phase 2 and beyond will introduce additional features based on my
              usage and requirements.
            </p>
          </div>
          <div>
            <h3 class="text-gray-300 mb-2">Features</h3>
            <ul class="ml-4 text-sm mb-2">
              <li>View favorite stock price trends on a daily time frame.</li>
              <li>
                Access various chart types, including volume charts and moving
                averages (MA).
              </li>
              <li>
                Select stocks from a predefined list to view their updated
                prices.
              </li>
              <li>
                Compare selected stocks with two default options: Apple and
                Google.
              </li>
              <li>
                Use a TradingView widget in the footer to check current prices
                conveniently.
              </li>
            </ul>
            <p class="text-sm">
              This app is designed to make tracking my favorite content simple,
              convenient, and tailored to my preferences.
            </p>
          </div>
        </div>
        <div id="image" class="p-2 m-auto">
          <NuxtImg src="/images/full-asset.png" width="450" class="rounded-2" />
        </div>
      </section>

      <section class="grid grid-cols-2 gap-4">
        <div class="p-2 m-auto flex justify-center items-center gap-8 text-3xl">
          <div class="i-logos-vue" />
          <div class="i-logos-nuxt-icon" />
          <div class="i-logos-unocss" />
          <NuxtImg
            src="/images/tv-logo.png"
            width="40"
            class="b-1 b-solid b-dark-4"
          />
        </div>
        <div>
          <h3 class="text-gray-300 mb-2">Stack and explanation</h3>
          <p class="text-sm">
            I chose to work with Nuxt.js for this project due to my proficiency
            with Vue.js and the need to support multiple pages and server-side
            rendering (SSR) for scalability in the future. Nuxt also simplifies
            routing, making it efficient for managing navigation between pages.
            Initially, I used Chart.js, a library I’m familiar with from my
            workplace. However, I later switched to TradingView's lightweight
            charts because they are more visually appealing and offer a wider
            variety of chart types for customization. For the data API, after
            extensive research, I selected Alpha Vantage. It stood out for its
            generous free-tier limit on daily API calls, making it the most
            convenient option for my needs.
          </p>
        </div>
      </section>

      <section class="grid grid-cols-2 gap-4">
        <div>
          <h3 class="text-gray-300 mb-2">Problems and thought process</h3>
          <p class="text-sm">
            At first, I integrated Supabase to display data fetched from the
            database. However, when the API limit became a constraint, I decided
            to bypass Supabase and display only the API's returned data
            directly. With a daily limit of 25 API calls, I focused on
            minimizing API usage. I generated multiple types of charts from a
            single API call and updated the data only when necessary.
            Additionally, I couldn’t retrieve index fund data, so I postponed
            implementing a comparison feature between index funds and selected
            stocks. As there are different types of charts available to
            visualize price trends, I experimented to find the ones that best
            suited my preferences. Since this was my first time using the
            library, I started with simple configurations and gradually added
            complexity as I became more familiar with its features.
          </p>
        </div>
        <div class="p-2 m-auto">
          <div
            class="i-ic-baseline-contact-support text-6xl text-blue-400 animate-pulse rotate-25"
          />
        </div>
      </section>

      <div>
        <h3 class="text-gray-300 mb-2">Lessons learned</h3>
        <p class="text-sm">
          The main lesson I learned is how to effectively use lightweight
          charts. Similar to my previous projects, I planned and implemented
          features throughout the development process, which involved many
          trials and errors. It also taught me the importance of adapting to
          limitations, such as API call restrictions, and finding creative
          solutions to overcome them.
        </p>
      </div>

      <div>
        <h3 class="text-gray-300 mb-2">Features plan to add later</h3>
        <ul class="ml-4 text-sm">
          <li>
            Add a new page for a watchlist table to track selected assets.
          </li>
          <li>
            Integrate fundamental data for each asset to provide more detailed
            insights.
          </li>
          <li>
            Implement charts for different time frames to analyze trends over
            various periods.
          </li>
          <li>
            Include a baseline chart within multi-type charts for easier
            comparison.
          </li>
          <li>
            Enhance the comparison functionality to support more detailed asset
            analysis.
          </li>
          <li>
            Add the ability to compare personal investment growth with stock
            performance.
          </li>
          <li>Enable comparisons between selected stocks and index funds.</li>
        </ul>
      </div>
    </div>
    <ScrollTop />
  </div>
</template>
