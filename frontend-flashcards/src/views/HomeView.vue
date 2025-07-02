<template>
  <div class="p-4">
    <h1 class="text-2xl font-bold">Frontend Interview Flashcards</h1>
    <p class="mt-2">Practice core frontend concepts with quick Q&A cards.</p>
  </div>
  <section class="p-4">
    <label for="tech" class="block mb-2 text-sm font-medium text-gray-700"
      >Choose a language</label
    >
    <select
      id="tech"
      v-model="selectedLanguage"
      name="Language"
      class="p-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 text-sm text-gray-700"
    >
      <option disabled value="">Select a language</option>
      <option value="html">HTML</option>
      <option value="js">JavaScript</option>
      <option value="css">CSS</option>
    </select>
  </section>
  <div class="grid gap-6 p-6 md:grid-cols-2 lg:grid-cols-3">
    <Flashcard
      v-for="(card, index) in paginatedQuestions"
      :key="index"
      :question="card.question"
      :answer="card.answer"
    />
  </div>
  <div class="flex justify-center items-center gap-4 p-4">
    <button
      :disabled="currentPage === 1"
      @click="goToNextPage"
      class="px-4 py-2 bg-blue-500 text-white rounded disabled:opacity-50"
    >
      Previous
    </button>
    <span class="text-gray-700 font-medium">Page {{ currentPage }}</span>
    <button
      :disabled="isLastPage"
      @click="goTopPreviousPage"
      class="px-4 py-2 bg-blue-500 text-white rounded disabled:opacity-50"
    >
      Next
    </button>
  </div>
</template>
<script setup>
import { ref, computed } from "vue";
import Flashcard from "@/components/Flashcard.vue";
import questionaire from "@/data/js-flashcards.json";
const selectedLanguage = ref("");
const questions = ref(questionaire);
const currentPage = ref(1);
const cardsPerPage = ref(10);
const paginatedQuestions = computed(() => {
  const startIndex = (currentPage.value - 1) * cardsPerPage.value;
  return questions.value.slice(startIndex, startIndex + cardsPerPage.value);
});
</script>
