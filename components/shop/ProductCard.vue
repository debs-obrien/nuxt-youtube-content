<template>
  <div>
    <button
      v-if="showRefresh"
      class="text-sm bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-2 rounded-full mb-4"
      @click="$fetch"
    >
      Refresh
    </button>
    <p v-if="$fetchState.pending">Fetching mountains...</p>
    <p v-else-if="$fetchState.error">An error occured :(</p>
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
        <!-- <NuxtLink
          :to="mountain.slug"
          class="block mt-1 text-lg leading-tight font-semibold text-gray-900 hover:underline"
          >{{ mountain.title }}
        </NuxtLink> -->
        <NuxtLink
          :to="`/async-data/axios/${mountain.slug}`"
          class="block mt-1 text-lg leading-tight font-semibold text-gray-900 hover:underline"
          >Axios- {{ mountain.title }}
        </NuxtLink>
        <NuxtLink
          :to="`/async-data/fetch/${mountain.slug}`"
          class="block mt-1 text-lg leading-tight font-semibold text-gray-900 hover:underline"
          >Fetch API- {{ mountain.title }}
        </NuxtLink>

        <p class="mt-2 text-gray-600">
          {{ mountain.description }}
        </p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  async fetch() {
    this.mountains = await fetch(
      'https://api.nuxtjs.dev/mountains'
    ).then((res) => res.json())
  },
  data() {
    return {
      mountains: [],
      showRefresh: false
    }
  }
}
</script>
<style scoped>
img {
  height: 120px;
  object-fit: cover;
}
</style>
