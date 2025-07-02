<template>
  <div class="w-80 h-48 perspective cursor-pointer" @click="flipped = !flipped">
    <div
      :class="[
        'relative w-full h-full duration-500 transform-style preserve-3d',
        flipped ? 'rotate-y-180' : ''
      ]"
    >
      <!-- Front (question) -->
      <div
        class="absolute w-full h-full backface-hidden bg-white rounded-lg shadow-md p-6 flex items-center justify-center text-center text-lg font-semibold"
      >
        {{ question }}
      </div>

      <!-- Back (answer) -->
      <div
        class="absolute w-full h-full backface-hidden bg-blue-100 rounded-lg shadow-md p-6 flex items-center justify-center text-center text-lg font-semibold rotate-y-180"
      >
        {{ answer }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Flashcard",
  props: {
    question: String,
    answer: String,
  },
  data() {
    return {
      flipped: false,
    };
  },
};
</script>
<style scoped>
.perspective {
  perspective: 1000px;
}
.backface-hidden {
  backface-visibility: hidden;
  -webkit-backface-visibility: hidden;
}
.rotate-y-180 {
  transform: rotateY(180deg);
}
.preserve-3d {
  transform-style: preserve-3d;
}
</style>
