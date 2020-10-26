<template>
  <div class="container mx-auto mt-10">
    <div v-if="error" class="text-red-700">
      <ErrorAlert :message="error.message" />
    </div>
    <div v-else class="relative py-16 bg-white overflow-hidden">
      <NuxtLink to="/products">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M10 19l-7-7m0 0l7-7m-7 7h18"
          />
        </svg>
        <span>Back</span>
      </NuxtLink>
      <div class="relative px-4 sm:px-6 lg:px-8">
        <div class="text-lg max-w-prose mx-auto mb-6">
          <p
            class="text-base text-center leading-6 text-indigo-600 font-semibold tracking-wide uppercase"
          >
            {{ mountain.continent }}
          </p>
          <h1
            class="mt-2 mb-8 text-3xl text-center leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl sm:leading-10"
          >
            {{ mountain.title }}
          </h1>
        </div>
        <figure>
          <img
            class="w-auto rounded-lg mx-auto"
            :src="mountain.image"
            :alt="mountain.title"
            width="1310"
            height="873"
          />
          <figcaption class="text-center">{{ mountain.title }}</figcaption>
        </figure>
        <div class="prose prose-lg text-gray-500 mx-auto">
          <ul>
            <li>
              <span class="font-bold">Height</span>: {{ mountain.height }}
            </li>
            <li>
              <span class="font-bold">Country</span>:
              <span v-for="country in mountain.countries" :key="country">
                {{ country }}
              </span>
            </li>
          </ul>
          <p>
            {{ mountain.description }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  // async asyncData({ params, $axios }) {
  //   try {
  //     const mountain = await $axios.$get(
  //       `https://api.nuxtjs.dev/mountains/${params.mountain}/debbie`
  //     )
  //     return { mountain }
  //   } catch (error) {
  //     return { error }
  //   }
  // }
  async asyncData({ params }) {
    try {
      const { data } = await axios.get(
        `https://api.nuxtjs.dev/mountains/${params.mountain}/debbie`
      )
      return { mountain: data }
    } catch (error) {
      return { error }
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
</style>
