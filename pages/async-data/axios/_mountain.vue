<template>
  <div class="container mx-auto text-center mt-10 text-xl">
    <ShopBackButton />
    <h1>Uisng Nuxt AsyncData Hook with Axios</h1>

    <div v-if="error" class="text-red-700">
      <ErrorAlert :message="error.message" />
    </div>

    <pre v-else>Mountain: {{ mountain }}</pre>
  </div>
</template>
<script>
export default {
  // ** Example using Nuxt asyncData hook with $axios **

  async asyncData({ params, $axios }) {
    try {
      const mountain = await $axios.$get(
        `https://api.nuxtjs.dev/mountains/${params.mountain}`
      )
      return { mountain }
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
