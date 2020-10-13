<template>
  <div>
    <h1>{{ post.title }}</h1>
    <p>{{ post.description }}</p>
  </div>
</template>

<script>
export default {
  async asyncData({ params, $axios }) {
    const post = await $axios.$get(`https://api.nuxtjs.dev/posts/${params.id}`)
    return { post }
  }
}
</script>
