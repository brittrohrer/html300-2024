<script setup>

import {ref} from "vue";

/* use variable that can be changed and create web content dynamically */
const title =ref(`Photography`);

</script>

<template>
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
</template>

<style scoped>
h1 {
    color: black;
}
</style>