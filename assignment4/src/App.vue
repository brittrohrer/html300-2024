<script setup>

// import components/nav pages
import { ref, computed } from "vue";
import Home from './components/Home.vue'
import AccordionPage from './components/AccordionPage.vue'
import GridPage from './components/GridPage.vue'
import ImagesPage from './components/ImagesPage.vue'

//create routes
const routes = {
  "/": Home,
  "/grid": GridPage,
  "/accordion": AccordionPage,
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
  <header class="bg-light">
    <h1>{{ title }}</h1>
    <nav class="navbar navbar-expand-sm bg-dark navbar-dark"> 
      <ul class="nav navbar-nav">
        <li class="nav-item"><a class="nav-link" href="#/">Home</a></li>
        <li class="nav-item"><a class="nav-link" href="#/images">Images Page</a></li>
        <li class="nav-item"><a class="nav-link" href="#/accordion">Accordion Page</a></li>
        <li class="nav-item"><a class="nav-link" href="#/grid">Grid Page</a></li>
        <component :is="currentView" />
      </ul>
    </nav>
  </header>
    <!-- might need to do if else to show correct main content when click -->

</template>

<style scoped>
  h1 {
    color: black;
  }
  header {
    width: 100%;
  }


@media (min-width: 1024px) {
  
}
</style>
