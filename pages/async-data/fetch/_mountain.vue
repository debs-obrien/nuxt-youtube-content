<template>
  <div class="container mx-auto text-center mt-10 text-xl">
    <ShopBackButton />

    <h1>Uisng Nuxt AsyncData Hook with Fetch API</h1>

    <div v-if="error" class="text-red-700">
      <ErrorAlert :message="error.message" />
    </div>

    <pre v-else>Mountain: {{ mountain }}</pre>
  </div>
</template>
<script>
export default {
  // ** Example Nuxt asyncData hook with js fetch method **

  async asyncData({ params, $axios }) {
    const mountain = await fetch(
      `https://api.nuxtjs.dev/mountains/${params.mountain}/debbie`
    ).then((res) => res.json())

    if (mountain.slug === params.mountain) {
      return { mountain }
    } else {
      throw new Error('API error')
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
