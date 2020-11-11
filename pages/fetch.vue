<template>
  <div>
    <div v-if="$fetchState.error" class="">
      <Error />
    </div>
    <div v-else class="container mx-auto text-center mt-10 text-xl">
      <BackButton />
      <h1>Nuxt Fetch Hook</h1>
      <div
        v-for="mountain in mountains"
        :key="mountain.title"
        class="mb-4 flex felx-col text-left md:flex"
      >
        <div class="md:flex-shrink-0">
          <img
            class="rounded-lg md:w-56"
            :src="mountain.image"
            :alt="mountain.title"
          />
        </div>
        <div class="mt-4 md:mt-0 md:ml-6">
          <div
            class="uppercase tracking-wide text-sm text-indigo-600 font-bold"
          >
            {{ mountain.continent }}
          </div>

          <p class="mt-2 text-gray-600">
            {{ mountain.description }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  async fetch() {
    const api = 'https://api.nuxtjs.dev/mountains/xxx'
    this.mountains = await this.$axios.$get(api)
  },
  data() {
    return {
      mountains: {}
    }
  }
}
</script>
<style scoped>
svg {
  width: 20px;
  height: 20px;
  display: inline-block;
}
img {
  height: 120px;
  object-fit: cover;
}
</style>
