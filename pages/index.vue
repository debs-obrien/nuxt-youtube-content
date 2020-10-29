<template>
  <div class="container">
    <div class="background-image">
      <Logo />
      <h1 class="title">Learn Nuxt with Debbie</h1>
    </div>
    <figure v-for="(item, i) in images" :key="i">
      <img
        class="w-auto rounded-lg mx-auto p-2"
        :src="require(`~/assets/${item}.jpg`)"
      />
    </figure>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: ['aconcagua', 'mont-blanc']
    }
  }
}
</script>

<style scoped>
.background-image {
  margin: 20px;
  padding: 20px;
  background: url('~assets/mont-blanc.jpg');
}
</style>
