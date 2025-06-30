<template>
<div class="p-4">
    <h1 class="text-2xl font-bold">Frontend Interview Flashcards</h1>
    <p class="mt-2">Practice core frontend concepts with quick Q&A cards.</p>
</div>
<section class="p-4">
<label for="tech" class="block mb-2 text-sm font-medium text-gray-700">Choose a language</label>
<select id="tech" v-model="selectedLanguage" name="Language"
  class="p-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 text-sm text-gray-700">
  <option disabled value="">Select a language</option>
  <option value="html">HTML</option>
  <option value="js">JavaScript</option>
  <option value="css">CSS</option>
</select>

</section>
</template>
<script setup>
import {ref} from 'vue';
const selectedLanguage = ref('');
</script>