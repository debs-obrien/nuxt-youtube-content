<template>
  <div class="container mx-auto">
    <h1 class="font-bold text-xl text-center">Mountains</h1>
    <NuxtLink to="/" class="text-left text-grey-600 hover:underline">
      Home
    </NuxtLink>
    <ShopProductCard />
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
