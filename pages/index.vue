<template>
  <div class="min-h-screen pb-16">
    <Header />
    <div class="showcase bg-blue-100 pt-16">
      <h1 class="text-center my-6 font-semibold text-3xl text-gray-800">
        Deine Job <br />
        Website
      </h1>
      <img class="mb-4" src="/agreement.svg" alt="agremend" />
      <img
        class="object-cover w-full relative -bottom-1 -z-1"
        src="wave-white.svg"
        alt="wave"
      />
    </div>

    <!-- tab selector button -->
    <tab-button
      @selectData="selectData"
      :tabData="tabData"
      :selectedTab="selectedTab"
    />
    <div>
      <div class="max-w-xs mx-auto">
        <p class="text-center text-2xl text-gray-700 my-6">
          {{ selectedTab.description }}
        </p>
      </div>
    </div>

    <!-- steps wrapper and container -->
    <step-container :selectedTab="selectedTab" />

    <Footer />
  </div>
</template>

<script>
import TabButton from "../components/tabButton.vue";
import stepContainer from "../components/steps/stepContainer.vue";
import Footer from "../components/footer.vue";
import Header from "../components/header.vue";

export default {
  components: { stepContainer },
  data() {
    return {
      tabData: [
        {
          id: 1,
          title: "Arbeitnehmer",
          description: "Drei einfache Schritte zu deinem neuen Job",
          step1: {
            imageUrl: "/tab1-step1.svg",
            text: "Erstellen dein Lebenslauf",
          },
          step2: {
            imageUrl: "/tab1-step2.svg",
            text: "Erhalte Vermittlungs- angebot von Arbeitgeber",
          },
          step3: {
            imageUrl: "/tab1-step3.svg",
            text: "Vermittlung nach Provision oder Stundenlohn",
          },
        },
        {
          id: 2,
          title: "Arbeitgeber",
          description: "Drei einfache Schritte zu deinem neuen Mitarbeiter",
          step1: {
            imageUrl: "/tab1-step1.svg",
            text: "Erstellen dein Lebenslauf",
          },
          step2: {
            imageUrl: "/tab2-step2.svg",
            text: "Erhalte Vermittlungs- angebot von Arbeitgeber",
          },
          step3: {
            imageUrl: "/tab2-step3.svg",
            text: "Wähle deinen neuen Mitarbeiter aus",
          },
        },
        {
          id: 3,
          title: "Temporärbüro",
          description:
            "Drei einfache Schritte zur Vermittlung neuer Mitarbeiter",
          step1: {
            imageUrl: "/tab1-step1.svg",
            text: "Erstellen dein Lebenslauf",
          },
          step2: {
            imageUrl: "/tab3-step2.svg",
            text: "Erhalte Vermittlungs- angebot von Arbeitgeber",
          },
          step3: {
            imageUrl: "/tab3-step3.svg",
            text: "Vermittlung nach Provision oder Stundenlohn",
          },
        },
      ],
      selectedTab: {},
    };
  },
  methods: {
    selectData(data) {
      this.selectedTab = data;
    },
  },
  created() {
    this.selectedTab = this.tabData[0];
  },
  watch: {
    selectedTab(newTab) {
      this.selectedTab = newTab;
    },
  },
};
</script>
