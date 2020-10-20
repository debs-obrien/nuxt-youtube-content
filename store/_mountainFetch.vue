<template>
  <div class="container mx-auto text-center mt-10 text-xl">
    <ShopBackButton />

    <h1>Uisng Nuxt AsyncData Hook with Fetch API</h1>

    <div v-if="error" class="text-red-700">
      <ErrorAlert :message="error.message" />
    </div>

    <pre v-else>{{ mountain }}</pre>
  </div>
</template>
<script>
export default {
  async asyncData({ params }) {
    try {
      const mountain = await fetch(
        `https://api.nuxtjs.dev/mountains/${params.mountain}`
      ).then((response) => {
        if (response.ok) {
          return response.json()
        }
        throw new Error('there has been a problem')
      })

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
