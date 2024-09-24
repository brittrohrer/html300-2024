<script setup>
import { ref, computed } from "vue";

// Page Elements Components
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
//Nav Pages/Components and Computing Current View

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




</script>

<template>
  <div> 
    <Header>
      <!-- This is the Header slot -->
    </Header>
    
    <!-- place component in the area of the main element so each nav link will place the content for each vue page in the desired area-->
    <component :is="currentView" />
    
    <Footer>
      <!-- This is the Footer slot -->
    </Footer>
    
  </div>  
</template>

<style scoped>
  h1,h4,p {
    color: black;
  }
  header {
    width: 100%;
  }


@media (min-width: 1024px) {
  
}
</style>
