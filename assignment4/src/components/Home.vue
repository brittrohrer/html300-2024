<script setup>
import { ref } from "vue";

const name = ref("Home");


const cards = ref([
                {
                    header: `Title 1`,
                    text: `Lorem ipsum dolor, sit amet consectetur adipisicing elit. Modi, debitis.`,
                    link: `"#"`,
                    button: `Link Button`
                },
                {
                    header: `Title 2`,
                    text: `Lorem ipsum dolor, sit amet consectetur adipisicing elit. Modi, debitis.`,
                    link: `"#"`,
                    button: `Link Button`
                },
                {
                    header: `Title 3`,
                    text: `Lorem ipsum dolor, sit amet consectetur adipisicing elit. Modi, debitis.`,
                    link: `"#"`,
                    button: `Link Button`
                },
            ],
);

</script>

<template>
    <main class="container">
        <div container d-flex flex-row justify-content-evenly mt-5 mb-5 flex-wrap gap-3>
            <div class="card" 
                style="width: 18rem;" 
                v-for="card in cards" :key="card.name">
                <div class="card-body">
                    <h3 class="card-title">
                    {{card.header}}</h3>
                    <p class="card-text">{{card.text}}</p>
                    <a href={{card.link}} 
                        class="btn btn-primary">
                        {{card.button}}</a>
                </div>
            </div>
        </div>
    </main>
    
</template>

<style scoped>

</style>