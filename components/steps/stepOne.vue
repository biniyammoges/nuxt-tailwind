<template>
  <!-- step 1 -->
  <div class="bg-white my-4 px-4 py-8">
    <img class="mx-auto mb-4" :src="stepData.imageUrl" alt="step" />
    <div class="flex items-end relative -top-6">
      <h1 class="text-9xl text-gray-500 mr-4 leading-none">1.</h1>
      <p class="text-lg text-gray-600 max-w-xs leading-5">
        {{ stepData.text }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["stepData"],
};
</script>
