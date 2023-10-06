<template>
  <app-accordion />
</template>

<script>
import AppAccordion from "./components/AppAccordion.vue";

export default {
  name: "App",
  components: { AppAccordion },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
