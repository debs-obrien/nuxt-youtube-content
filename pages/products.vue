<template>
  <div class="container mx-auto">
    <h1 class="font-bold text-xl text-center">Mountains</h1>
    <NuxtLink to="/" class="text-left text-grey-600 hover:underline">
      Home
    </NuxtLink>
    <ProductCard
      v-for="mountain in mountains"
      :key="mountain.title"
      :product="mountain"
      class="mb-4 flex felx-col text-left"
    />
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
      mountains: []
    }
  }
}
</script>
<style lang="postcss">
img {
  height: 120px;
}
</style>
