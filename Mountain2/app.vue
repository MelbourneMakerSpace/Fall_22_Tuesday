<template>
  <div>
    <h1>Mountains</h1>
    <div
      v-for="mountain of mountainData"
      class="flex flex-row gap-5 mb-5 bg-blue-300 mx-5 p-5 rounded"
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
