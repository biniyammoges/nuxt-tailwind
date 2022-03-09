<template>
  <!-- step 3 -->
  <div class="bg-white relative px-4 py-12">
    <img
      class="w-full absolute -top-12 right-0 left-0"
      src="/wave-white-1.svg"
      alt="wave"
    />
    <div class="flex items-end relative -top-6">
      <h1 class="text-9xl text-gray-500 mr-4 leading-none">3.</h1>
      <p class="text-lg text-gray-600 max-w-xs leading-5">
        {{ stepData.text }}
      </p>
    </div>
    <img class="mx-auto mb-4" :src="stepData.imageUrl" alt="step" />
  </div>
</template>

<script>
export default {
  props: ["stepData"],
};
</script>
