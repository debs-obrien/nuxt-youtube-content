<template>
  <div class="md:flex">
    <div class="md:flex-shrink-0">
      <img
        class="rounded-lg md:w-56"
        :src="product.image"
        :alt="product.title"
      />
    </div>
    <div class="mt-4 md:mt-0 md:ml-6">
      <div class="uppercase tracking-wide text-sm text-indigo-600 font-bold">
        {{ product.continent }}
      </div>
      <NuxtLink
        :to="product.slug"
        class="block mt-1 text-lg leading-tight font-semibold text-gray-900 hover:underline"
        >{{ product.title }}
      </NuxtLink>
      <p class="mt-2 text-gray-600">
        {{ product.description }}
      </p>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    product: {
      type: Object,
      default: () => {}
    }
  }
}
</script>
