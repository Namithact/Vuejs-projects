<template>
  <div id="app" class="min-h-screen bg-gray-50 text-gray-900">
    <header class="bg-white shadow p-4 flex justify-between items-center">
      <div class="flex">
      <img src="./assets/logo.png"  alt="Logo" class="h-10 w-auto mr-4" />
      <h1 class="text-xl font-bold">Flashcard App</h1>
      </div>
      <nav class="space-x-4">
        <router-link to="/" class="text-blue-600 hover:underline" active-class="font-bold underline"
  exact-active-class="text-blue-900">Home</router-link>
        <router-link to="/about" class="text-blue-600 hover:underline" active-class="font-bold underline"
  exact-active-class="text-blue-900">About</router-link>
      </nav>
    </header>

    <main class="p-4">
      <router-view />
    </main>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
/* Optional global styles */
</style>
