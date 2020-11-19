<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">{{ title }}</h1>
      <NuxtLink to="/about" class="button--green">About</NuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Home page with Nuxt'
    }
  },
  head() {
    return {
      title: this.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Home page description'
        }
      ]
    }
  }
}
</script>
