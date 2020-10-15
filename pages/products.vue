<template>
  <div class="container mx-auto">
    <h1 class="font-bold text-xl text-center">Mountains</h1>
    <NuxtLink to="/" class="text-left text-grey-600 hover:underline">
      Home
    </NuxtLink>
    <button
      class="text-sm bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-2 rounded-full mb-4"
      @click="showMountains"
    >
      Show Mountains
    </button>
    <LazyShopProductCard v-if="show" />
  </div>
</template>
<script>
export default {
  data() {
    return {
      show: false
    }
  },
  methods: {
    showMountains() {
      this.show = true
    }
  }
}
</script>
