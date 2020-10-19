<template>
  <div class="container mx-auto text-center mt-10 text-xl">
    <ShopBackButton />

    <h1>Using Nuxt Fetch Hook with Axios</h1>

    <p v-if="$fetchState.pending">loading...</p>

    <p v-else-if="$fetchState.error" class="text-red-700">
      <ErrorAlert :message="$fetchState.error.message" />
    </p>

    <pre v-else>Mountain: {{ mountain }}</pre>
  </div>
</template>
<script>
export default {
  // ** Example Nuxt fetch hook with $axios **

  async fetch() {
    this.mountain = await this.$axios.$get(
      `https://api.nuxtjs.dev/mountains/${this.$route.params.mountain}/debbie`
    )
  },
  data() {
    return {
      mountain: {} // needed if using Nuxt fetch hook
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
