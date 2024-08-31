<script setup>
import { ref } from "vue";

const name = ref("Home");

const touchButton = ref(true);

const jumboTitle = ref(`Jumbotron Title`);
const jumboText = ref(`Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium debitis facere, 
                        vitae in iste beatae quidem repudiandae optio dignissimos eos cupiditate suscipit 
                        explicabo nihil atque et molestias, ratione maxime repellat eaque exercitationem quaerat 
                        ipsa similique excepturi voluptatibus. Quibusdam placeat blanditiis sunt modi quas recusandae, 
                        saepe laboriosam ea facilis. Pariatur reiciendis beatae quod atque quas inventore unde assumenda 
                        debitis incidunt itaque.`);

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
        <div class= "toggle-button">
            <p v-if="touchButton">Don't click the button ;)</p>
            <p v-else>Well ... you clicked the button :p</p>

            <button class="btn btn-danger" @click="touchButton = !touchButton">This is the button</button>
        </div>
        <div class="jumbotron jumbotron-fluid bg-info">
                <!--create jumbotron container with top margin of 2 and padding 2-->
                <div class="container mt-5 p-2">
                    <h2 class="display-4">{{jumboTitle}}</h2>
                    <!--create top margin of 2 text and emphasize text with "lead"-->
                    <p class="lead mt-2">{{jumboText}}</p>
                </div>
            </div>
        <div class= "container d-flex flex-row justify-content-evenly mt-5 mb-5 flex-wrap gap-3">
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
    p, h2 {
        color: black;
    }
    .toggle-button {
        margin-top: 2rem;
    }
</style>