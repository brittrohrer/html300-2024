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

/* use variable that can be changed and create web content dynamically */
const title =ref(`Website Name`);

const footerTitle = ref (`Footer Info`);
const footerText= ref(`Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat, incidunt maiores eos quis quo cupiditate 
            et odit laudantium a impedit nesciunt autem? Exercitationem cum laborum repudiandae animi. Neque, repudiandae 
            nihil a molestias natus corporis vero culpa praesentium provident optio aspernatur! Accusantium ipsam quis, 
            voluptas ut laborum perferendis. Quas, quidem modi?`);

</script>

<template>
  <div>
    <!--create header with title and navigation routes and the footer to be used accross all web pages while the main content changes based on the current path selected -->
    <header class="bg-light">
      <h1>{{ title }}</h1>
      <nav class="navbar navbar-expand-sm bg-dark navbar-dark"> 
        <ul class="nav navbar-nav">
          <li class="nav-item"><a class="nav-link" href="#/">Home</a></li>
          <li class="nav-item"><a class="nav-link" href="#/images">Images Page</a></li>
          <li class="nav-item"><a class="nav-link" href="#/accordion">Accordion Page</a></li>
          <li class="nav-item"><a class="nav-link" href="#/grid">Grid Page</a></li>
        </ul>
      </nav>
    </header>
    <!-- place component in the area of the main element so each nav link will place the content for each vue page in the desired area-->
    <component :is="currentView" />

    <footer class="footer bg-light mt-auto">
      <h4 class="text-center">{{footerTitle}}</h4>
        <p>{{footerText}}</p>
    </footer>
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
