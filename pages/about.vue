<template>
  <div class="container">
    <div>
      <h1 class="title">About</h1>
      <p v-if="$nuxt.isOffline">oops you are offline 😱</p>
      <p v-if="$nuxt.isOnline">yeahhhh 😍</p>
      <NuxtLink to="/" class="button--green">Home</NuxtLink>
    </div>
  </div>
</template>
