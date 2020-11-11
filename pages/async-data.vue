<template>
  <div class="container mx-auto text-center mt-10 text-xl">
    <BackButton />
    <h1>Nuxt AsyncData Hook</h1>
    <p v-if="error" class="text-red-700">
      <ErrorAlert :message="error.message" />
    </p>
    <div
      v-for="mountain in mountains"
      v-else
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
        <div class="uppercase tracking-wide text-sm text-indigo-600 font-bold">
          {{ mountain.continent }}
        </div>
        <p class="mt-2 text-gray-600">
          {{ mountain.description }}
        </p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios, redirect }) {
    const api = 'https://api.nuxtjs.dev/mountains/xxx'

    try {
      const mountains = await $axios.$get(api)
      return { mountains }
    } catch (error) {
      redirect('/error')
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
