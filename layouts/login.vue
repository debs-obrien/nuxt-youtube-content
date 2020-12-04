<template>
  <!-- component -->
  <div class="font-mono bg-gray-400">
    <!-- Container -->
    <div class="container mx-auto">
      <div class="flex justify-center px-6 my-12 w-full">
        <!-- Row -->
        <div class="w-full xl:w-3/4 lg:w-11/12 flex">
          <!-- Col -->
          <div
            class="w-full h-auto bg-gray-400 hidden lg:block lg:w-1/2 bg-cover rounded-l-lg"
            style="background-image: url('/login.jpeg')"
          ></div>
          <!-- Col -->
          <div
            class="w-full lg:w-1/2 bg-white p-5 rounded-lg lg:rounded-l-none"
          >
            <Nuxt />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
