<template>
  <div class="my-4">
    <step-one :stepData="selectedTab.step1" />
    <step-two :stepData="selectedTab.step2" />
    <step-three :stepData="selectedTab.step3" />
  </div>
</template>

<script>
import StepTwo from "./stepTwo.vue";
import StepThree from "./stepThree.vue";
import StepOne from "./stepOne.vue";

export default {
  components: { StepTwo, StepThree, StepOne },
  props: ["selectedTab"],
};
</script>
