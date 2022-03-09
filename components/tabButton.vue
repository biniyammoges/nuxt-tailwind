<template>
  <div
    class="w-min mx-auto border flex justify-center rounded-2xl my-2 mx-4 border-gray-200 center z-10 overflow-hidden whitespace-nowrap"
  >
    <button
      @click="selectData(data)"
      class="inline-block py-2 px-2 border-r last:border-none border-gray-200"
      :class="{
        'bg-green-300': selectedTab.id === data.id,
        'text-white': selectedTab.id === data.id,
        'text-green-600': selectedTab.id !== data.id,
      }"
      href="#"
      v-for="data in tabData"
      :key="data.id"
    >
      {{ data.title }}
    </button>
  </div>
</template>

<script>
export default {
  props: ["selectedTab", "tabData"],
  methods: {
    selectData(data) {
      this.$emit("selectData", data);
    },
  },
  watch: {
    selectedTab(newData) {
      this.selectedTab = newData;
    },
  },
};
</script>
