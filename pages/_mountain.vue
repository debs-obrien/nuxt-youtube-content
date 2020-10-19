<template>
  <div class="container mx-auto text-center mt-10 text-xl">
    <h1>differences between Nuxt asyncData and fetch</h1>
    <p>
      Also, note that the fetch hook of Nuxt is awaited on SSR so there is not
      loading placeholder It’s only on client side navigation where you will
      have the placeholder. I recommend to use SSR for demo And add another page
      to show the client side navigation to demonstrate the difference between
      asyncData and fetch
    </p>
    <!-- <p v-if="$fetchState.pending">loading...</p>

    <p v-else-if="$fetchState.error" class="text-red-700">
      <ErrorAlert :message="$fetchState.error.message" />
    </p> -->

    <div v-if="error" class="text-red-700">
      <ErrorAlert :message="error.message" />
    </div>

    <pre v-else>Mountain: {{ mountain }}</pre>
  </div>
</template>
<script>
export default {
  // ** Example Nuxt asyncData hook with js fetch method **

  // async asyncData({ params, $axios }) {
  //   try {
  //     const mountain = await fetch(
  //       `https://api.nuxtjs.dev/mountains/${params.mountain}/debbie`
  //     ).then((res) => res.json())
  //     return { mountain }
  //   } catch (error) {
  //     return { error }
  //   }
  // },

  // ** Example Nuxt fetch hook with js fetch method **

  // async fetch() {
  //   this.mountain = await fetch(
  //     `https://api.nuxtjs.dev/mountains/${this.$route.params.mountain}/debbie`
  //   )
  //     .then((res) => res.json())
  //     .catch(function (error) {
  //       return error
  //     })
  // },
  // ** Example using Nuxt asyncData hook with $axios **

  async asyncData({ params, $axios }) {
    try {
      const mountain = await $axios.$get(
        `https://api.nuxtjs.dev/mountains/${params.mountain}/debbie`
      )

      return { mountain }
    } catch (error) {
      return { error }
    }
  },

  // ** Example Nuxt fetch hook with $axios **

  // async fetch() {
  //   this.mountain = await this.$axios.$get(
  //     `https://api.nuxtjs.dev/mountains/${this.$nuxt.context.params.mountain}`
  //   )
  // },

  data() {
    return {
      mountain: {} // needed if using Nuxt fetch
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
