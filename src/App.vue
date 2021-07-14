<template>
  <PriceSection />
</template>

<script>
import PriceSection from "./components/PriceSection.vue";

export default {
  name: "App",
  components: {
    PriceSection,
  },
};
</script>

<style>
@import "./assets/reset.css";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
