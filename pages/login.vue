<template>
  <!-- component -->
  <div>
    <h3 class="pt-4 text-2xl text-center">Welcome Back!</h3>
    <form class="px-8 pt-6 pb-8 mb-4 bg-white rounded">
      <div class="mb-4">
        <label
          class="block mb-2 text-sm font-bold text-gray-700"
          for="username"
        >
          Username
        </label>
        <input
          id="username"
          class="w-full px-3 py-2 text-sm leading-tight text-gray-700 border rounded shadow appearance-none focus:outline-none focus:shadow-outline"
          type="text"
          placeholder="Username"
        />
      </div>
      <div class="mb-4">
        <label
          class="block mb-2 text-sm font-bold text-gray-700"
          for="password"
        >
          Password
        </label>
        <input
          id="password"
          class="w-full px-3 py-2 mb-3 text-sm leading-tight text-gray-700 border border-red-500 rounded shadow appearance-none focus:outline-none focus:shadow-outline"
          type="password"
          placeholder="******************"
        />
        <p class="text-xs italic text-red-500">Please choose a password.</p>
      </div>
      <div class="mb-4">
        <input id="checkbox_id" class="mr-2 leading-tight" type="checkbox" />
        <label class="text-sm" for="checkbox_id"> Remember Me </label>
      </div>
      <div class="mb-6 text-center">
        <button
          class="w-full px-4 py-2 font-bold text-white bg-blue-500 rounded-full hover:bg-blue-700 focus:outline-none focus:shadow-outline"
          type="button"
        >
          Sign In
        </button>
      </div>
      <hr class="mb-6 border-t" />
      <div class="text-center">
        <a
          class="inline-block text-sm text-blue-500 align-baseline hover:text-blue-800"
          href="./register.html"
        >
          Create an Account!
        </a>
      </div>
      <div class="text-center">
        <a
          class="inline-block text-sm text-blue-500 align-baseline hover:text-blue-800"
          href="./forgot-password.html"
        >
          Forgot Password?
        </a>
      </div>
    </form>
  </div>
</template>
<script>
export default {
  layout: 'login'
}
</script>
