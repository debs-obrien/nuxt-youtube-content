<template>
  <div class="container mx-auto">
    <div class="relative py-16 bg-white overflow-hidden">
      <NuxtLink to="/products">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M10 19l-7-7m0 0l7-7m-7 7h18"
          />
        </svg>
        <span>Back</span>
      </NuxtLink>
      <div class="relative px-4 sm:px-6 lg:px-8">
        <div class="text-lg max-w-prose mx-auto mb-6">
          <p
            class="text-base text-center leading-6 text-indigo-600 font-semibold tracking-wide uppercase"
          >
            Sount America
          </p>
          <h1
            class="mt-2 mb-8 text-3xl text-center leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl sm:leading-10"
          >
            Aconcagua
          </h1>
        </div>
        <figure>
          <img
            class="w-auto rounded-lg mx-auto"
            src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4e/Aconcagua2016.jpg/600px-Aconcagua2016.jpg"
            alt=""
            width="1310"
            height="873"
          />
          <figcaption class="text-center">Aconcagua</figcaption>
        </figure>
        <div class="prose prose-lg text-gray-500 mx-auto">
          <ul>
            <li><span class="font-bold">Height</span>: 6,962 m</li>
            <li><span class="font-bold">Country</span>: Argentina</li>
          </ul>
          <p>
            Aconcagua is a mountain in the Principal Cordillera of the Andes
            mountain range, in Mendoza Province, Argentina. It is the highest
            mountain in the Americas and the highest outside of Asia, being the
            highest in both the Southern and Western Hemispheres with a summit
            elevation of 6,960.8 metres.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
svg {
  width: 20px;
  height: 20px;
  display: inline-block;
}
</style>
