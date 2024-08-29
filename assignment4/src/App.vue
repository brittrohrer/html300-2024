<script setup>

// import components/nav pages
import { ref, computed } from "vue";
import Home from './components/Home.vue'
import AccordianPage from './components/AccordianPage.vue'
import GridPage from './components/GridPage.vue'
import ImagesPage from './components/ImagesPage.vue'

//create routes
const routes = {
  "/": Home,
  "/grid": GridPage,
  "/accordian": AccordianPage,
  "/images": ImagesPage
};

//find current path using the window.location.hash and change the value of hash based on the nav link clicked
const currentPath = ref(window.location.hash);

window.addEventListener("hashchange", () => {
  currentPath.value = window.location.hash;
});

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || "/"] // || NotFound;
});

const title =ref(`Website Name`);
</script>

<template>
  <header>
      <h1>{{ title }}</h1>
      <a href="#/">Home</a>
      <a href="#/grid">Grid Page</a>
      <a href="#/accordian">Accordian Page</a>
      <a href="#/images">Images Page</a>
      <component :is="currentView" />
  </header>
  <!-- might need to do if else to show correct main content when click -->

</template>

<style scoped>
  h1 {
    color: white;
  }
  a {
    color: yellow;
  }

@media (min-width: 1024px) {
  
}
</style>
