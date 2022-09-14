<template>
  <div>
    <h1>Mountains - Updated Sept 13</h1>
    <!-- <div
      v-for="mountain of mountainData"
      class="flex flex-row gap-5 p-5 mx-5 mb-5 bg-blue-300 rounded"
    >
      <div style="width: 30%; margin-top: auto; margin-bottom: auto">
        <img :src="mountain.image" style="width: 100%; height: auto" />
      </div>
      <div
        style="width: 60%; display: flex; flex-direction: column; gap: 0.5em"
      >
        <div style="font-weight: bold; font-size: larger">
          {{ mountain.title }}
          <span style="font-weight: normal; font-size: small">
            ({{ mountain.height }})</span
          >
        </div>

        <div>{{ mountain.description }}</div>
      </div>
    </div> -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4">
      <div class="p-4" v-for="mountain of mountainData">
        <div
          class="h-full overflow-hidden border-2 border-gray-200 rounded-lg border-opacity-60"
        >
          <img
            class="object-cover object-center w-full lg:h-48 md:h-36"
            :src="mountain.image"
            alt="blog"
          />
          <div class="p-6">
            <h2
              class="mb-1 text-xs font-medium tracking-widest text-gray-400 title-font"
            >
              {{ mountain.height }}
            </h2>
            <h1 class="mb-3 text-lg font-medium text-gray-900 title-font">
              {{ mountain.title }}
            </h1>
            <p class="mb-3 leading-relaxed">
              {{ mountain.description }}
            </p>
            <div class="flex flex-wrap items-center">
              <a
                class="inline-flex items-center text-indigo-500 md:mb-2 lg:mb-0"
                >Learn More
                <svg
                  class="w-4 h-4 ml-2"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                  stroke-width="2"
                  fill="none"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <path d="M5 12h14"></path>
                  <path d="M12 5l7 7-7 7"></path>
                </svg>
              </a>
              <span
                class="inline-flex items-center py-1 pr-3 ml-auto mr-3 text-sm leading-none text-gray-400 border-r-2 border-gray-200 lg:ml-auto md:ml-0"
              >
                <svg
                  class="w-4 h-4 mr-1"
                  stroke="currentColor"
                  stroke-width="2"
                  fill="none"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  viewBox="0 0 24 24"
                >
                  <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path>
                  <circle cx="12" cy="12" r="3"></circle></svg
                >1.2K
              </span>
              <span
                class="inline-flex items-center text-sm leading-none text-gray-400"
              >
                <svg
                  class="w-4 h-4 mr-1"
                  stroke="currentColor"
                  stroke-width="2"
                  fill="none"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M21 11.5a8.38 8.38 0 01-.9 3.8 8.5 8.5 0 01-7.6 4.7 8.38 8.38 0 01-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 01-.9-3.8 8.5 8.5 0 014.7-7.6 8.38 8.38 0 013.8-.9h.5a8.48 8.48 0 018 8v.5z"
                  ></path></svg
                >6
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const {
  data: mountainData,
  pending,
  error,
  refresh,
} = await useFetch('https://api.nuxtjs.dev/mountains', { server: false })
</script>
