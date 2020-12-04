<template>
  <div>
    <img src="~/assets/logo.svg" />
    <h1>{{ title }} 👋</h1>
    <ul>
      <li v-for="mountain in mountains" :key="mountain.title">
        <NuxtLink
          :to="{ name: 'mountains-slug', params: { slug: mountain.slug } }"
        >
          {{ mountain.title }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  async asyncData() {
    const mountains = await fetch(
      'https://api.nuxtjs.dev/mountains'
    ).then((res) => res.json())
    return { mountains }
  },
  data() {
    return {
      title: 'Hello Nuxters!'
    }
  },
  head() {
    return {
      title: this.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content:
            'The amazing Nuxt application that teaches me all the cool features of Nuxt'
        }
      ]
    }
  }
}
</script>
