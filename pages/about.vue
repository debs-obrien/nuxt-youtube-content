<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">About Page</h1>
      <NuxtLink to="/" class="button--green">Home</NuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  head: {
    title: 'Learn Nuxt with Debbie about page',
    meta: [
      { charset: 'utf-8' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        hid: 'description',
        name: 'description',
        content: 'my amazing application about page'
      },
      { name: 'twitter:site', content: 'debs_obrien' },
      { name: 'twitter:card', content: 'summary_large_image' },
      {
        hid: 'twitter:url',
        name: 'twitter:url',
        content: 'https://debbie.codes'
      },
      {
        hid: 'twitter:title',
        name: 'twitter:title',
        content: 'My amazing website'
      },
      {
        hid: 'twitter:description',
        name: 'twitter:description',
        content: 'This blog post is incredible.'
      },
      {
        hid: 'twitter:image',
        name: 'twitter:image',
        content: '/icon.png'
      }
    ],
    link: [
      { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' },
      { rel: 'stylesheet', href: 'https://fonts.xz.style/serve/inter.css' },
      {
        rel: 'stylesheet',
        href:
          'https://cdn.jsdelivr.net/npm/@exampledev/new.css@1.1.2/new.min.css'
      },
      {
        rel: 'stylesheet',
        href: 'https://fonts.googleapis.com/css?family=Roboto&display=swap'
      }
    ],
    script: [
      {
        src: 'https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js'
      }
    ]
  }
}
</script>
<style scoped>
h1 {
  font-family: Roboto, sans-serif;
}
</style>
