<template>
  <div
    class="bg-red-100 border border-red-400 text-red-700 px-4 py-3 rounded relative"
    role="alert"
  >
    <p>
      <strong>😔 Looks like we have a problem</strong>
    </p>
    <p class="block sm:inline"><strong>Error:</strong> {{ message }}</p>
  </div>
</template>
<script>
export default {
  props: {
    message: {
      type: String,
      default: '() => {}'
    }
  }
}
</script>
