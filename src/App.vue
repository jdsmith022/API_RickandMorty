<template>
  <div id="app">
    <NavBar />
    <MainSection />
    <Footer />
  </div>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import MainSection from "./components/MainSection.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    NavBar,
    MainSection,
    Footer
  }
};
</script>
